---
title: 提供程序错误 （访问桌面数据库参考 （英文）
TOCTitle: Provider errors
ms:assetid: 9c39d450-6e67-b2fd-aeb5-849e6b65fd54
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249710(v=office.15)
ms:contentKeyID: 48546592
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d175cdaa007a354d12304dceff0352a923de2291
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717641"
---
# <a name="provider-errors"></a><span data-ttu-id="94374-102">提供程序错误</span><span class="sxs-lookup"><span data-stu-id="94374-102">Provider errors</span></span>


<span data-ttu-id="94374-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="94374-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="94374-p101">发生提供程序错误时，将返回运行时错误 -2147467259。收到此错误时，请检查活动 **Connection** 对象的 **Errors** 集合，该集合将包含描述所发生情况的一个或多个错误。</span><span class="sxs-lookup"><span data-stu-id="94374-p101">When a provider error occurs, a run-time error of -2147467259 is returned. When you receive this error, check the active **Connection** object's **Errors** collection, which will contain one or more errors describing what happened.</span></span>

## <a name="the-ado-errors-collection"></a><span data-ttu-id="94374-106">ADO Errors 集合</span><span class="sxs-lookup"><span data-stu-id="94374-106">The ADO Errors Collection</span></span>

<span data-ttu-id="94374-p102">由于特定 ADO 操作可以产生多个提供程序错误，因此 ADO 通过 **Connection** 对象来公开错误对象集合。如果操作最后成功完成，则此集合不包含任何对象；如果出现问题并且提供程序引发了一个或多个错误，则此集合包含一个或多个 **Error** 对象。通过分别检查各个错误对象，可以确定错误的确切原因。</span><span class="sxs-lookup"><span data-stu-id="94374-p102">Because a particular ADO operation can produce multiple provider errors, ADO exposes a collection of error objects through the **Connection** object. This collection contains no objects if an operation concludes successfully and contains one or more **Error** objects if something went wrong and the provider raised one or more errors. Examine each individual error object in order to determine the exact cause of the error.</span></span>

<span data-ttu-id="94374-p103">在处理完已发生的任何错误之后，可以调用 **Clear** 方法来清除该集合。特别重要的是：在调用 **Recordset** 对象的 **Resync** 、 **UpdateBatch** 或 **CancelBatch** 方法，或调用 **Connection** 对象的 **Open** 方法，或设置 **Recordset** 对象的 **Filter** 属性之前，一定要显式清除 **Errors** 集合。通过显式清除该集合，可以确保集合中不会留下上一个操作产生的任何 **Error** 对象。</span><span class="sxs-lookup"><span data-stu-id="94374-p103">Once you have finished handling any errors that have occurred, you can clear the collection by calling the **Clear** method. It is particularly important to explicitly clear the **Errors** collection before you call the **Resync**, **UpdateBatch**, or **CancelBatch** method on a **Recordset** object, the **Open** method on a **Connection** object, or set the **Filter** property on a **Recordset** object. By clearing the collection explicitly, you can be certain that any **Error** objects in the collection are not left over from a previous operation.</span></span>

<span data-ttu-id="94374-p104">某些操作可以生成警告以及错误。警告也是由 **Errors** 集合中的 **Error** 对象来表示的。提供程序向集合添加警告时，它不会生成运行时错误。请检查 **Errors** 集合的 **Count** 属性以确定警告是否是由特定操作产生的。如果计数是一或更大的数，则已有 **Error** 对象添加到集合中。一旦确定 **Errors** 集合包含错误或警告，就可以迭代遍历此集合，并检索出此集合包含的每个 **Error** 对象的相关信息。以下简短 Visual Basic 示例演示此情况：</span><span class="sxs-lookup"><span data-stu-id="94374-p104">Some operations can generate warnings as well as errors. Warnings are also represented by **Error** objects in the **Errors** collection. When a provider adds a warning to the collection, it does not generate a run-time error. Check the **Count** property of the **Errors** collection to determine if a warning was produced by a particular operation. If the count is one or greater, an **Error** object has been added to the collection. Once you have determined that the **Errors** collection contains errors or warnings, you can iterate through the collection and retrieve information about each of the **Error** objects it contains. The following short Visual Basic example demonstrates this:</span></span>

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

<span data-ttu-id="94374-p105">错误处理例程包括一个 **For Each** 循环，用于检查 **Errors** 集合中的每个对象。在此示例中，它只是积累消息并进行显示。在工作程序中，需要编写代码，以便针对每个错误执行合适的任务，例如，关闭所有打开的文件，以及按次序关闭程序。</span><span class="sxs-lookup"><span data-stu-id="94374-p105">The error-handling routine includes a **For Each** loop that examines each object in the **Errors** collection. In this example, it simply accumulates a message for display. In a working program, you would write code to perform an appropriate task for each error, such as closing all open files and shutting down the program in an orderly fashion.</span></span>

## <a name="the-error-object"></a><span data-ttu-id="94374-123">Error 对象</span><span class="sxs-lookup"><span data-stu-id="94374-123">The Error Object</span></span>

<span data-ttu-id="94374-p106">通过检查 **Error** 对象，可以确定发生了什么错误，更重要的是，可以确定什么应用程序或对象导致了错误。 **Error** 对象有以下属性：</span><span class="sxs-lookup"><span data-stu-id="94374-p106">By examining an **Error** object you can determine what error occurred, and more importantly, what application or what object caused the error. The **Error** object has the following properties:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="94374-126">属性名称</span><span class="sxs-lookup"><span data-stu-id="94374-126">Property name</span></span></p></th>
<th><p><span data-ttu-id="94374-127">说明</span><span class="sxs-lookup"><span data-stu-id="94374-127">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94374-128"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="94374-128"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-129">所发生的错误的文本说明。</span><span class="sxs-lookup"><span data-stu-id="94374-129">A text description of the error that occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94374-130"><strong>HelpContext HelpFile</strong></span><span class="sxs-lookup"><span data-stu-id="94374-130"><strong>HelpContext, HelpFile</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-131">指的是帮助主题和帮助文件（其中包含对所发生的错误的说明）。</span><span class="sxs-lookup"><span data-stu-id="94374-131">Refers to the help topic and help file that contain a description of the error that occurred.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94374-132"><strong>NativeError</strong></span><span class="sxs-lookup"><span data-stu-id="94374-132"><strong>NativeError</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-133">提供程序特定的错误号。</span><span class="sxs-lookup"><span data-stu-id="94374-133">The provider-specific error number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94374-134"><strong>Number</strong></span><span class="sxs-lookup"><span data-stu-id="94374-134"><strong>Number</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-135">长整型，表示已发生的错误号（在 <strong>ErrorValueEnum</strong> 中列出）。</span><span class="sxs-lookup"><span data-stu-id="94374-135">A Long Integer that represents the number (listed in the <strong>ErrorValueEnum</strong>) of the error that occurred.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94374-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="94374-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-137">指示生成错误的对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="94374-137">Indicates the name of the object or application that generated an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94374-138"><strong>SQLState</strong></span><span class="sxs-lookup"><span data-stu-id="94374-138"><strong>SQLState</strong></span></span></p></td>
<td><p><span data-ttu-id="94374-139">五字符的错误代码，该代码是在处理 SQL 语句期间由提供程序返回的。</span><span class="sxs-lookup"><span data-stu-id="94374-139">A five-character error code that the provider returns during the process of a SQL statement.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="94374-p107">ADO **Error** 对象与标准的 Visual Basic **Err** 对象很相似。它的属性描述了发生的错误。除了错误号外，您还会收到两个相关的信息片段。 **NativeError** 属性包含您正在使用的提供程序特有的错误号。在上一个示例中，提供程序是 Microsoft OLE DB Provider for SQL Server，所以 **NativeError** 将包含特定于 SQL Server 的错误。 **SQLState** 属性有五个字母组成的代码，用于描述 SQL 语句中的错误。</span><span class="sxs-lookup"><span data-stu-id="94374-p107">The ADO **Error** object is quite similar to the standard Visual Basic **Err** object. Its properties describe the error that occurred. In addition to the number of the error, you also receive two related pieces of information. The **NativeError** property contains an error number specific to the provider you are using. In the previous example, the provider is the Microsoft OLE DB Provider for SQL Server, so **NativeError** will contain errors specific to SQL Server. The **SQLState** property has a five-letter code that describes an error in a SQL statement.</span></span>

## <a name="event-related-errors"></a><span data-ttu-id="94374-146">与事件相关的错误</span><span class="sxs-lookup"><span data-stu-id="94374-146">Event-Related Errors</span></span>

<span data-ttu-id="94374-p108">在发生与事件相关的错误时，也会使用 **Error** 对象。通过检查作为事件参数传递的 **Error** 对象，可以确定在引发 ADO 事件的过程中是否发生了错误。</span><span class="sxs-lookup"><span data-stu-id="94374-p108">The **Error** object is also used when event-related errors occur. You can determine if an error occurred in the process that raised an ADO event by checking the **Error** object passed as an event parameter.</span></span>

<span data-ttu-id="94374-p109">如果导致事件的操作最后成功结束，则事件处理程序的 *adStatus* 参数将设置为 *adStatusOK*。另一方面，如果引发事件的操作不成功，则 *adStatus* 参数将设置为 *adStatusErrorsOccurred*。在该情况下，*pError* 参数将包含用于描述错误的 **Error** 对象。</span><span class="sxs-lookup"><span data-stu-id="94374-p109">If the operation that causes an event is concluded successfully, the *adStatus* parameter of the event handler will be set to *adStatusOK*. On the other hand, if the operation that raised the event was unsuccessful, the *adStatus* parameter is set to *adStatusErrorsOccurred*. In that case, the *pError* parameter will contain an **Error** object that describes the error.</span></span>

