---
title: 提供程序错误 （访问桌面数据库参考 （英文）
TOCTitle: Provider Errors
ms:assetid: 9c39d450-6e67-b2fd-aeb5-849e6b65fd54
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249710(v=office.15)
ms:contentKeyID: 48546592
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 18d226ff8ff270705d8e30425f83eabc289383b1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883244"
---
# <a name="provider-errors"></a>提供程序错误


**适用于**： Access 2013、 Office 2013 

发生提供程序错误时，将返回运行时错误 -2147467259。收到此错误时，请检查活动 **Connection** 对象的 **Errors** 集合，该集合将包含描述所发生情况的一个或多个错误。

## <a name="the-ado-errors-collection"></a>ADO Errors 集合

由于特定 ADO 操作可以产生多个提供程序错误，因此 ADO 通过 **Connection** 对象来公开错误对象集合。如果操作最后成功完成，则此集合不包含任何对象；如果出现问题并且提供程序引发了一个或多个错误，则此集合包含一个或多个 **Error** 对象。通过分别检查各个错误对象，可以确定错误的确切原因。

在处理完已发生的任何错误之后，可以调用 **Clear** 方法来清除该集合。特别重要的是：在调用 **Recordset** 对象的 **Resync** 、 **UpdateBatch** 或 **CancelBatch** 方法，或调用 **Connection** 对象的 **Open** 方法，或设置 **Recordset** 对象的 **Filter** 属性之前，一定要显式清除 **Errors** 集合。通过显式清除该集合，可以确保集合中不会留下上一个操作产生的任何 **Error** 对象。

某些操作可以生成警告以及错误。警告也是由 **Errors** 集合中的 **Error** 对象来表示的。提供程序向集合添加警告时，它不会生成运行时错误。请检查 **Errors** 集合的 **Count** 属性以确定警告是否是由特定操作产生的。如果计数是一或更大的数，则已有 **Error** 对象添加到集合中。一旦确定 **Errors** 集合包含错误或警告，就可以迭代遍历此集合，并检索出此集合包含的每个 **Error** 对象的相关信息。以下简短 Visual Basic 示例演示此情况：

```vb 
 
' BeginErrorHandlingVB02 
Private Function DeleteCustomer(ByVal CompanyName As String) As Long 
 On Error GoTo DeleteCustomerError 
 
 rst.Find "CompanyName='" & CompanyName & "'" 
 
DeleteCustomerError: 
 
 Dim objError As ADODB.Error 
 Dim strError As String 
 
 If cnn.Errors.Count > 0 Then 
 For Each objError In cnn.Errors 
 strError = strError & "Error #" & objError.Number & _ 
 " " & objError.Description & vbCrLf & _ 
 "NativeError: " & objError.NativeError & vbCrLf & _ 
 "SQLState: " & objError.SQLState & vbCrLf & _ 
 "Reported by: " & objError.Source & vbCrLf & _ 
 "Help file: " & objError.HelpFile & vbCrLf & _ 
 "Help Context ID: " & objError.HelpContext 
 Next 
 MsgBox strError 
 End If 
End Function 
' EndErrorHandlingVB02 
```

错误处理例程包括一个 **For Each** 循环，用于检查 **Errors** 集合中的每个对象。在此示例中，它只是积累消息并进行显示。在工作程序中，需要编写代码，以便针对每个错误执行合适的任务，例如，关闭所有打开的文件，以及按次序关闭程序。

## <a name="the-error-object"></a>Error 对象

通过检查 **Error** 对象，可以确定发生了什么错误，更重要的是，可以确定什么应用程序或对象导致了错误。 **Error** 对象有以下属性：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>所发生的错误的文本说明。</p></td>
</tr>
<tr class="even">
<td><p><strong>HelpContext HelpFile</strong></p></td>
<td><p>指的是帮助主题和帮助文件（其中包含对所发生的错误的说明）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NativeError</strong></p></td>
<td><p>提供程序特定的错误号。</p></td>
</tr>
<tr class="even">
<td><p><strong>编号</strong></p></td>
<td><p>长整型，表示已发生的错误号（在 <strong>ErrorValueEnum</strong> 中列出）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>指示生成错误的对象或应用程序的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>SQLState</strong></p></td>
<td><p>五字符的错误代码，该代码是在处理 SQL 语句期间由提供程序返回的。</p></td>
</tr>
</tbody>
</table>


ADO **Error** 对象与标准的 Visual Basic **Err** 对象很相似。它的属性描述了发生的错误。除了错误号外，您还会收到两个相关的信息片段。 **NativeError** 属性包含您正在使用的提供程序特有的错误号。在上一个示例中，提供程序是 Microsoft OLE DB Provider for SQL Server，所以 **NativeError** 将包含特定于 SQL Server 的错误。 **SQLState** 属性有五个字母组成的代码，用于描述 SQL 语句中的错误。

## <a name="event-related-errors"></a>与事件相关的错误

在发生与事件相关的错误时，也会使用 **Error** 对象。通过检查作为事件参数传递的 **Error** 对象，可以确定在引发 ADO 事件的过程中是否发生了错误。

如果导致事件的操作最后成功结束，则事件处理程序的 *adStatus* 参数将设置为 *adStatusOK*。另一方面，如果引发事件的操作不成功，则 *adStatus* 参数将设置为 *adStatusErrorsOccurred*。在该情况下，*pError* 参数将包含用于描述错误的 **Error** 对象。

