---
title: 非同步用戶端通訊端範例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous client sockets
- sockets, code examples
- sockets, asynchronous client sockets
ms.assetid: d4ac53a0-b50b-4232-9726-d47d25fcc38a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d295841173ee2f3bf018a2058b4eac1629c4828f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-client-socket-example"></a>非同步用戶端通訊端範例
下列範例程式會建立連線到伺服器的用戶端。 伺服器已內建非同步通訊端，因此在伺服器傳回回應時，不會暫停執行用戶端應用程式。 應用程式會將字串傳送到伺服器，然後在主控台上顯示伺服器所傳回的字串。  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Threading  
Imports System.Text  
  
' State object for receiving data from remote device.  
  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing  
    ' Size of receive buffer.  
    Public Const BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(BufferSize) As Byte  
    ' Received data string.  
    Public sb As New StringBuilder  
End Class 'StateObject  
  
Public Class AsynchronousClient  
    ' The port number for the remote device.  
    Private Const port As Integer = 11000  
  
    ' ManualResetEvent instances signal completion.  
    Private Shared connectDone As New ManualResetEvent(False)  
    Private Shared sendDone As New ManualResetEvent(False)  
    Private Shared receiveDone As New ManualResetEvent(False)  
  
    ' The response from the remote device.  
    Private Shared response As String = String.Empty  
  
    Public Shared Sub Main()  
        ' Establish the remote endpoint for the socket.  
        ' For this example use local machine.  
        Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
        Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
        Dim remoteEP As New IPEndPoint(ipAddress, port)  
  
        ' Create a TCP/IP socket.  
        Dim client As New Socket(ipAddress.AddressFamily, SocketType.Stream, ProtocolType.Tcp)  
  
        ' Connect to the remote endpoint.  
        client.BeginConnect(remoteEP, New AsyncCallback(AddressOf ConnectCallback), client)  
  
        ' Wait for connect.  
        connectDone.WaitOne()  
  
        ' Send test data to the remote device.  
        Send(client, "This is a test<EOF>")  
        sendDone.WaitOne()  
  
        ' Receive the response from the remote device.  
        Receive(client)  
        receiveDone.WaitOne()  
  
        ' Write the response to the console.  
        Console.WriteLine("Response received : {0}", response)  
  
        ' Release the socket.  
        client.Shutdown(SocketShutdown.Both)  
        client.Close()  
    End Sub 'Main  
  
    Private Shared Sub ConnectCallback(ByVal ar As IAsyncResult)  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    End Sub 'ConnectCallback  
  
    Private Shared Sub Receive(ByVal client As Socket)  
  
        ' Create the state object.  
        Dim state As New StateObject  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0, New AsyncCallback(AddressOf ReceiveCallback), state)  
    End Sub 'Receive  
  
    Private Shared Sub ReceiveCallback(ByVal ar As IAsyncResult)  
  
        ' Retrieve the state object and the client socket   
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, bytesRead))  
  
            ' Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0, New AsyncCallback(AddressOf ReceiveCallback), state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    End Sub 'ReceiveCallback  
  
    Private Shared Sub Send(ByVal client As Socket, ByVal data As String)  
        ' Convert the string data to byte data using ASCII encoding.  
        Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
        ' Begin sending the data to the remote device.  
        client.BeginSend(byteData, 0, byteData.Length, 0, New AsyncCallback(AddressOf SendCallback), client)  
    End Sub 'Send  
  
    Private Shared Sub SendCallback(ByVal ar As IAsyncResult)  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    End Sub 'SendCallback  
End Class 'AsynchronousClient  
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Threading;  
using System.Text;  
  
// State object for receiving data from remote device.  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
  
public class AsynchronousClient {  
    // The port number for the remote device.  
    private const int port = 11000;  
  
    // ManualResetEvent instances signal completion.  
    private static ManualResetEvent connectDone =   
        new ManualResetEvent(false);  
    private static ManualResetEvent sendDone =   
        new ManualResetEvent(false);  
    private static ManualResetEvent receiveDone =   
        new ManualResetEvent(false);  
  
    // The response from the remote device.  
    private static String response = String.Empty;  
  
    private static void StartClient() {  
        // Connect to a remote device.  
        try {  
            // Establish the remote endpoint for the socket.  
            // The name of the   
            // remote device is "host.contoso.com".  
            IPHostEntry ipHostInfo = Dns.GetHostEntry("host.contoso.com");  
            IPAddress ipAddress = ipHostInfo.AddressList[0];  
            IPEndPoint remoteEP = new IPEndPoint(ipAddress, port);  
  
            // Create a TCP/IP socket.  
            Socket client = new Socket(ipAddress.AddressFamily,  
                SocketType.Stream, ProtocolType.Tcp);  
  
            // Connect to the remote endpoint.  
            client.BeginConnect( remoteEP,   
                new AsyncCallback(ConnectCallback), client);  
            connectDone.WaitOne();  
  
            // Send test data to the remote device.  
            Send(client,"This is a test<EOF>");  
            sendDone.WaitOne();  
  
            // Receive the response from the remote device.  
            Receive(client);  
            receiveDone.WaitOne();  
  
            // Write the response to the console.  
            Console.WriteLine("Response received : {0}", response);  
  
            // Release the socket.  
            client.Shutdown(SocketShutdown.Both);  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
    }  
  
    private static void ConnectCallback(IAsyncResult ar) {  
        try {  
            // Retrieve the socket from the state object.  
            Socket client = (Socket) ar.AsyncState;  
  
            // Complete the connection.  
            client.EndConnect(ar);  
  
            Console.WriteLine("Socket connected to {0}",  
                client.RemoteEndPoint.ToString());  
  
            // Signal that the connection has been made.  
            connectDone.Set();  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
    }  
  
    private static void Receive(Socket client) {  
        try {  
            // Create the state object.  
            StateObject state = new StateObject();  
            state.workSocket = client;  
  
            // Begin receiving the data from the remote device.  
            client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
                new AsyncCallback(ReceiveCallback), state);  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
    }  
  
    private static void ReceiveCallback( IAsyncResult ar ) {  
        try {  
            // Retrieve the state object and the client socket   
            // from the asynchronous state object.  
            StateObject state = (StateObject) ar.AsyncState;  
            Socket client = state.workSocket;  
  
            // Read data from the remote device.  
            int bytesRead = client.EndReceive(ar);  
  
            if (bytesRead > 0) {  
                // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
  
                // Get the rest of the data.  
                client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                    new AsyncCallback(ReceiveCallback), state);  
            } else {  
                // All the data has arrived; put it in response.  
                if (state.sb.Length > 1) {  
                    response = state.sb.ToString();  
                }  
                // Signal that all bytes have been received.  
                receiveDone.Set();  
            }  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
    }  
  
    private static void Send(Socket client, String data) {  
        // Convert the string data to byte data using ASCII encoding.  
        byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
        // Begin sending the data to the remote device.  
        client.BeginSend(byteData, 0, byteData.Length, 0,  
            new AsyncCallback(SendCallback), client);  
    }  
  
    private static void SendCallback(IAsyncResult ar) {  
        try {  
            // Retrieve the socket from the state object.  
            Socket client = (Socket) ar.AsyncState;  
  
            // Complete sending the data to the remote device.  
            int bytesSent = client.EndSend(ar);  
            Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
            // Signal that all bytes have been sent.  
            sendDone.Set();  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
    }  
  
    public static int Main(String[] args) {  
        StartClient();  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a>請參閱  
 [非同步伺服器通訊端範例](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)  
 [使用同步伺服器通訊端](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [通訊端程式碼範例](../../../docs/framework/network-programming/socket-code-examples.md)
