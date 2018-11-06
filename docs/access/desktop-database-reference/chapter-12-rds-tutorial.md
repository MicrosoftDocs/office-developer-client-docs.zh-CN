---
title: 第 12 章： 远程数据服务 (RDS) 教程
TOCTitle: 'Chapter 12: RDS tutorial'
ms:assetid: fa44a5e8-e4df-dfdd-d7a1-a870ec3cabdd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250277(v=office.15)
ms:contentKeyID: 48548837
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fb29fd070a693b608cede1d21329b3749c18e852
ms.sourcegitcommit: 007141520d6479860f452371532f9267f33eb260
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25999499"
---
# <a name="chapter-12-remote-data-service-rds-tutorial"></a>第 12 章： 远程数据服务 (RDS) 教程

**适用于**： Access 2013、 Office 2013

本教程演示如何使用 RDS 编程模型查询和更新数据源 首先，它介绍完成此任务所需的步骤。 然后，可在 Microsoft Visual Basic Scripting Edition 和 Microsoft Visual J + + 中，其中 ADO for Windows Foundation Classes (ADO/WFC) 重复教程。

本教程使用不同语言的代码，主要有以下两个原因：

- 假设 RDS 文档的读者使用 Visual Basic 编码。这使得文档方便了 Visual Basic 编程人员，但对于使用其他语言的编程人员则没有多少用处。

- 如果您不太熟悉具体的 RDS 功能，但对于其他语言有所了解，那么可以通过在其他语言中寻求相同的功能来解决问题。

本教程基于 RDS 编程模型，并对该编程模型的每个步骤分别进行讨论，另外，还使用 Visual Basic 代码段举例讲述每个步骤。

代码示例使用其他语言重复演示，但是对其很少进行讨论。在采用给定编程语言的教程中，每个步骤都以编程模型和说明性教程中的相应步骤来标记。请使用步骤编号来引用说明性教程中的讨论。

下面对 RDS 编程模型进行了说明。在使用本教程时可将其作为路线图。

### <a name="rds-programming-model-with-objects"></a>RDS 编程模型与对象

- 指定要在服务器上调用的程序，并获取从客户端引用它的方法（代理）。

- 调用服务器程序，将参数传递给标识数据源和所发命令的服务器程序。

- 服务器程序通常是通过使用 ADO 从数据源获取 [Recordset](recordset-object-ado.md) 对象。可以选择在服务器上处理 **Recordset** 对象。

- 服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。

- 在客户端上，可以选择将 **Recordset** 对象置为便于可视控件使用的形式。

- 将对于 **Recordset** 对象进行的更改发回到服务器并将其用于更新数据源。

## <a name="step-1-specify-a-server-program"></a>步骤 1： 指定服务器程序

在大多数情况下，使用 [RDS.DataSpace](dataspace-object-rds.md) 对象的 [CreateObject](createobject-method-rds.md) 方法指定默认服务器程序 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或自定义服务器程序（业务对象）。服务器程序在服务器上实例化，返回的是对服务器程序的引用（即*代理*）。

本教程使用默认服务器程序：

```vb 
 
Sub RDSTutorial1() 
 Dim DS as New RDS.DataSpace 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
... 
``` 

## <a name="step-2-invoke-the-server-program"></a>步骤 2： 调用服务器程序 

当调用客户端*代理*上的某种方法时，服务器上的实际程序将执行该方法。在该步骤中，将在服务器上执行查询。

### <a name="part-a"></a>部分 A

如果您没有在本教程使用[RDSServer.DataFactory](datafactory-object-rdsserver.md) ，最方便的方式执行此步骤是使用[rds.DataControl](datacontrol-object-rds.md)对象。 **RDS.DataControl** 将该步骤与上一步（创建代理）合并，用于发出查询。

1. 设置**rds.DataControl**对象[服务器](server-property-rds.md)属性来确定应实例化服务器程序。

2. 设置[Connect](connect-property-rds.md)属性来指定要访问数据源的连接字符串。

3. 设置[SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado)属性指定的查询命令文本。 

4. 问题的[Refresh](refresh-method-rds.md)方法会导致服务器程序连接到数据源，检索指定的查询中的行，并返回到客户端**Recordset**对象。

本教程不使用 **RDS.DataControl** ，但在这里给出了它的形式：

```vb 
 
Sub RDSTutorial2A() 
 Dim DC as New RDS.DataControl 
 DC.Server = "https://yourServer" 
 DC.Connect = "DSN=Pubs" 
 DC.SQL = "SELECT * FROM Authors" 
 DC.Refresh 
... 
```

<br/>

本教程不使用 ADO 对象调用 RDS，但在这里给出了它的形式：

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
"Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
```

### <a name="part-b"></a>部分 B

执行此步骤的常规方法是调用**RDSServer.DataFactory**对象的[Query](query-method-rds.md)方法。 该方法使用一个连接字符串（用来连接到数据源）和一个命令文本（用来指定要从数据源中返回的行）。

本教程使用 **DataFactory** 对象的 **Query** 方法：

```vb 
 
Sub RDSTutorial2B() 
 Dim DS as New RDS.DataSpace 
 Dim DF 
 Dim RS as ADODB.Recordset 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

## <a name="step-3-server-obtains-a-recordset"></a>步骤 3： 服务器获取 Recordset 

服务器程序使用连接字符串和命令文本在数据源中查询所需的行。尽管也可以使用其他 Microsoft 数据访问接口（如 OLE DB），但通常使用 ADO 来检索该 **Recordset** 。

自定义服务器程序的形式可以类似如下：

```vb 
 
Public Function ServerProgram(cn as String, qry as String) as Object 
Dim rs as New ADODB.Recordset 
 rs.CursorLocation = adUseClient 
 rs.Open qry, cn 
 rs.ActiveConnection = Nothing 
 Set ServerProgram = rs 
End Function 
```

## <a name="step-4-server-returns-the-recordset"></a>步骤 4： 服务器返回 Recordset 

RDS 将检索到的 **Recordset** 对象转换为可以发回到客户端的形式（即，它*封送 ***Recordset**）。转换的确切形式及其发送方式取决于服务器是位于 Internet、Intranet 还是局域网上，或者服务器是否为动态链接库。但是，该细节并不是关键；RDS 将 **Recordset** 发回到客户端才是关键。

在客户端上， **Recordset** 对象返回，并被分配给本地变量。

```vb 
 
Sub RDSTutorial4() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

## <a name="step-5-datacontrol-is-made-usable"></a>步骤 5: DataControl 由可用 

所返回的 **Recordset** 对象已经可以使用。可以像对任何其他 **Recordset** 一样检查、定位或编辑该对象。对 **Recordset** 可以执行的操作取决于相应的环境。Visual Basic 和 Visual C++ 具有一些可视控件，这些控件可以直接或通过启用数据控件间接使用 **Recordset** 。

例如，如果您要显示在 Internet Explorer 中的网页，您可能想要在可视控件中显示的**Recordset**对象的数据。 网页上的可视控件不能直接访问**Recordset**对象。 但是，它们可以通过 **RDS.DataControl** 访问 [Recordset](datacontrol-object-rds.md) 对象。 当 **RDS.DataControl** 的 [SourceRecordset](recordset-sourcerecordset-properties-rds.md) 属性设置为 **Recordset** 对象时，RDS.DataControl 便可被可视控件使用。

可视控件对象的 **DATASRC** 参数必须设置为 **RDS.DataControl** ，它的 **DATAFLD** 属性必须设置为 **Recordset** 对象字段（列）。

在本教程中，设置 **SourceRecordset** 属性：

```vb 
 
Sub RDSTutorial5() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DC as New RDS.DataControl 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
 DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
... 
```

## <a name="step-6-changes-are-sent-to-the-server"></a>步骤 6： 将更改发送到服务器

如果对 **Recordset** 对象进行编辑，则可以将任何更改（即，对行进行地添加、更改或删除）发回到服务器。

[!注释] RDS 的默认行为可通过 ADO 对象和 Microsoft OLE DB Remoting Provider 隐式调用。 查询可以返回**记录集**，并将已编辑的**记录集**可以更新数据源。 本教程不通过 ADO 对象调用 RDS，但在这里给出了它的形式：

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
 "Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
... ' Edit the Recordset. 
rs.UpdateBatch ' The equivalent of SubmitChanges. 
... 
```

### <a name="part-a"></a>部分 A

假设这种情况下，仅使用[rds.DataControl](datacontrol-object-rds.md)和**Recordset**对象是否立即与**rds.DataControl**。 如果 [Server](submitchanges-method-rds.md) 和 **Connect** 属性已设置， [SubmitChanges](server-property-rds.md) 方法将用对 [Recordset](connect-property-rds.md) 对象进行的任何更改来更新数据源。

```vb 
 
Sub RDSTutorial6A() 
Dim DC as New RDS.DataControl 
Dim RS as ADODB.Recordset 
DC.Server = "https://yourServer" 
DC.Connect = "DSN=Pubs" 
DC.SQL = "SELECT * FROM Authors" 
DC.Refresh 
... 
Set RS = DC.Recordset 
 ' Edit the Recordset. 
... 
DC.SubmitChanges 
... 
```

### <a name="part-b"></a>部分 B

此外，您无法使用[RDSServer.DataFactory](datafactory-object-rdsserver.md)对象，指定连接和**Recordset**对象更新服务器。

```vb 
 
Sub RDSTutorial6B() 
Dim DS As New RDS.DataSpace 
Dim RS As ADODB.Recordset 
Dim DC As New RDS.DataControl 
Dim DF As Object 
Dim blnStatus As Boolean 
Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
 ' Edit the Recordset. 
blnStatus = DF.SubmitChanges "DSN=Pubs", RS 
End Sub 
```


## <a name="appendix-a-rds-tutorial-vbscript"></a>附录 a: RDS 教程 (VBScript)

这是在 Microsoft Visual Basic Scripting Edition 编写的 RDS 教程。 本教程的用途的说明，请参阅本主题介绍。

在本教程中， [rds.DataControl](datacontrol-object-rds.md)和[rds.DataSpace](dataspace-object-rds.md)在设计时; 创建即是与 object 标记中定义的。 另外，它们也可以在运行时通过 **Server.CreateObject** 方法创建。 

例如， **RDS.DataControl** 对象可以按如下方式创建：

```vb
    Set DC = Server.CreateObject("RDS.DataControl") 
     <!-- RDS.DataControl --> 
     <OBJECT 
     ID="DC1" CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E33"> 
     </OBJECT> 
     
     <!-- RDS.DataSpace --> 
     <OBJECT 
     ID="DS1" WIDTH=1 HEIGHT=1 
     CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E36"> 
     </OBJECT> 
     
     <SCRIPT LANGUAGE="VBScript"> 
     
     Sub RDSTutorial() 
     Dim DF1 
```

### <a name="step-1-specify-a-server-program"></a>步骤 1： 指定服务器程序

VBScript 可以发现 IIS web 服务器通过访问供 Active Server Pages 的 VBScript **Request.ServerVariables**方法运行的名称：

```vb 
 
"https://<%=Request.ServerVariables("SERVER_NAME")%>" 
```

但是，本教程使用虚构服务器"yourServer"。

> [!NOTE]
> [!注释] 请留意 **ByRef** 参数的数据类型。VBScript 不允许指定变量类型，因此必须始终传递变量。使用 HTTP 时，如果您用 **RDS.DataSpace** 对象的 [CreateObject](createobject-method-rds.md) 方法调用服务器程序，RDS 将允许您向应该使用非变量的方法传递变量。在使用 DCOM 或进程内服务器时，必须使客户端与服务器端的参数类型相匹配，否则将会产生"类型不匹配"错误。

```vb
 
Set DF1 = DS1.CreateObject("RDSServer.DataFactory", "https://yourServer") 
```

### <a name="step-2-part-a-invoke-the-server-program-with-rdsdatacontrol"></a>步骤 2，部件答： 调用服务器程序与 rds.DataControl

以下示例只是注释，演示 **RDS.DataControl** 的默认行为是执行指定的查询。

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial2A() 
 Dim RS 
 DC1.Refresh 
 Set RS = DC1.Recordset 
... 
```

跳到下面的步骤。

### <a name="step-4-server-returns-the-recordset"></a>步骤 4： 服务器返回 Recordset

```vb
 
Set RS = DF1.Query("DSN=Pubs;", "SELECT * FROM Authors") 
```

### <a name="step-5-datacontrol-is-made-usable-by-visual-controls"></a>步骤 5: DataControl 进行可用可视控件

```vb
 
' Assign the returned recordset to the DataControl. 
 
DC1.SourceRecordset = RS 
```

### <a name="step-6-part-a-changes-are-sent-to-the-server-with-rdsdatacontrol"></a>步骤 6，部件答： 更改发送到的服务器与 rds.DataControl

以下示例只是一个注释，演示 **RDS.DataControl** 如何执行更新。

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial6A() 
Dim RS 
DC1.Refresh 
... 
Set RS = DC1.Recordset 
' Edit the Recordset object... 
' The SERVER and CONNECT properties are already set from Step 2A. 
Set DC1.SourceRecordset = RS 
... 
DC1.SubmitChanges 
```

### <a name="step-6-part-b-changes-are-sent-to-the-server-with-rdsserverdatafactory"></a>步骤 6，部件 b： 将更改发送到使用 RDSServer.DataFactory 服务器

```vb
 
DF.SubmitChanges"DSN=Pubs", RS 
 
End Sub 
</SCRIPT> 
</BODY> 
</HTML> 
```

## <a name="appendix-b-rds-tutorial-visual-j"></a>附录 b: RDS 教程 （Visual J + +）

ADO/WFC 不完全遵循 RDS 对象模型，因为它不实现 [RDS.DataControl](datacontrol-object-rds.md) 对象。ADO/WFC 仅实现客户端类 [RDS.DataSpace](dataspace-object-rds.md)。

**DataSpace** 类实现 [CreateObject](createobject-method-rds.md) 方法，该方法返回 [ObjectProxy](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/objectproxy-ado-wfc-syntax) 对象。 **DataSpace** 类还实现 [InternetTimeout](internettimeout-property-rds.md) 属性。

**ObjectProxy** 类实现 call 方法，该方法可以调用任何服务器端业务对象。

```java 
 
import com.ms.wfc.data.*; 
public class RDSTutorial 
{ 
 public void tutorial() 
 { 
// Step 1: Specify a server program. 
 ObjectProxy obj = 
 DataSpace.createObject( 
 "RDSServer.DataFactory", 
 "https://YourServer"); 
 
// Step 2: Server returns a Recordset. 
 Recordset rs = (Recordset) obj.call( 
 "Query", 
 new Object[] {"DSN=Pubs;", "SELECT * FROM Authors"}); 
 
// Step 3: Changes are sent to the server. 
 ... // Edit Recordset. 
 obj.call( 
 "SubmitChanges", 
 new Object[] {"DSN=Pubs;", rs}); 
 return; 
 } 
} 
```



