---
<<<<<<< 标头标题： ConnectionString、 ConnectionTimeout 和 State 属性示例 （VJ + +） TOCTitle: ConnectionString、 ConnectionTimeout 和 State 属性示例 （VJ + +） === 标题： ConnectionString，ConnectionTimeout 和 State 属性示例 （VJ + +） TOCTitle: ConnectionString、 ConnectionTimeout 和 State 属性示例 （VJ + +）
>>>>>>> 母版页 ms:assetid: 88b3f95e-0e46-7cbb-8086-d583319a6628 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249599(v=office.15) ms:contentKeyID: 48546141 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="connectionstring-connectiontimeout-and-state-properties-example-vj"></a>ConnectionString、ConnectionTimeout 和 State 属性示例 (VJ++)
=======
# <a name="connectionstring-connectiontimeout-and-state-properties-example-vj"></a>ConnectionString、 ConnectionTimeout 和 State 属性示例 （VJ + +）
>>>>>>> master


**适用于**： Access 2013 |Office 2013

此示例演示使用 [ConnectionString](connectionstring-property-ado.md) 属性打开 [Connection](connection-object-ado.md) 对象的不同方式。它还使用 [ConnectionTimeout](connectiontimeout-property-ado.md) 属性设置一个连接超时时间，并使用 [State](state-property-ado.md) 属性来检查连接的状态。若要运行此过程，必须使用 GetState 函数。

```java 
 
// BeginConnectionStringJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class ConnectionStringX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 ConnectionStringX(); 
 System.exit(0); 
 } 
 
 // ConnectionStringX function 
 
 static void ConnectionStringX() 
 { 
 // Define ADO Objects. 
 Connection cnConn1 = null; 
 Connection cnConn2 = null; 
 Connection cnConn3 = null; 
 Connection cnConn4 = null; 
 
 //Declarations. 
 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String line = null; 
 String strTemp; 
 
 try 
 { 
 // Open a connection using OLE DB syntax. 
 cnConn1 = new Connection(); 
 cnConn1.setConnectionString( 
 "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"); 
 cnConn1.setCommandTimeout(30); 
 cnConn1.open(); 
 strTemp = getState(cnConn1.getState()); 
 System.out.println("CnConn1 state: " + strTemp); 
 
 // Open a connection using a DSN and ODBC tags. 
 // It is assumed that you have create DSN 'Pubs' with a user name as 
 // 'MyUserId' and password as 'MyPassword'. 
 cnConn2 = new Connection(); 
 cnConn2.setConnectionString("DSN='Pubs';UID='MyUserId';PWD='MyPassword';"); 
 cnConn2.open(); 
 strTemp = getState(cnConn2.getState()); 
 System.out.println("CnConn2 state: " + strTemp); 
 
 // Open a connection using a DSN and OLE DB tags. 
 cnConn3 = new Connection(); 
 cnConn3.setConnectionString 
 ("Data Source='Pubs';"); 
 cnConn3.open(); 
 strTemp = getState(cnConn3.getState()); 
 System.out.println("CnConn3 state: " + strTemp); 
 
 // Open a connection using a DSN and individual 
 // arguments instead of a connection string. 
 // It is assumed that you have create DSN 'Pubs' with a user name as 
 // 'MyUserId' and password as 'MyPassword'. 
 cnConn4 = new Connection(); 
 cnConn4.open("Pubs", "MyUserId", "MyPassword"); 
 strTemp = getState(cnConn4.getState()); 
 System.out.println("CnConn4 state: " + strTemp); 
 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 System.out.println("Exception: " + ae.getMessage()); 
 
 } 
 
 // System read requires this catch. 
 catch( java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (cnConn1 != null) 
 if (cnConn1.getState() == 1) 
 cnConn1.close(); 
 if (cnConn2 != null) 
 if (cnConn2.getState() == 1) 
 cnConn2.close(); 
 if (cnConn3 != null) 
 if (cnConn3.getState() == 1) 
 cnConn3.close(); 
 if (cnConn4 != null) 
 if (cnConn4.getState() == 1) 
 cnConn4.close(); 
 } 
 
 } 
 
 // getState Function 
 
 static String getState(int intState) 
 { 
 // Returns current state of the connection object. 
 String strState=null; 
 
 switch(intState) 
 { 
 case AdoEnums.ObjectState.CLOSED : 
 strState = new String("adStateClosed"); 
 break; 
 case AdoEnums.ObjectState.OPEN : 
 strState = new String("adStateOpen"); 
 break; 
 default : 
 break; 
 } 
 return strState; 
 } 
 
 // PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
 
// EndConnectionStringJ 
```

