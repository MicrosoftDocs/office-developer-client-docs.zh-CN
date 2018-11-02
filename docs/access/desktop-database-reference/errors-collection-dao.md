---
title: Errors 集合 (DAO)
TOCTitle: Errors Collection
ms:assetid: d42007b5-6410-14e9-baf9-9306fdef38f9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834805(v=office.15)
ms:contentKeyID: 48547929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: db6796d5777af12d1cd0a3e65647d7223f4423ba
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928920"
---
# <a name="errors-collection-dao"></a><span data-ttu-id="68aba-102">Errors 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="68aba-102">Errors collection (DAO)</span></span>


<span data-ttu-id="68aba-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="68aba-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="68aba-104">**Errors** 集合包含所有存储的 **Error** 对象，这些对象中的每一个都与一个涉及 DAO 的操作有关。</span><span class="sxs-lookup"><span data-stu-id="68aba-104">An **Errors** collection contains all stored **Error** objects, each of which pertains to a single operation involving DAO.</span></span>

## <a name="remarks"></a><span data-ttu-id="68aba-105">注解</span><span class="sxs-lookup"><span data-stu-id="68aba-105">Remarks</span></span>

<span data-ttu-id="68aba-p101">任何涉及 DAO 对象的操作都可以生成一个或多个错误。每个错误发生时，系统会将一个或多个 **Error** 对象放在 **DBEngine** 对象的 **Errors** 集合中。当另一个 DAO 操作生成错误时，将清除 **Errors** 集合，并将一组新的 **Error** 对象放在 **Errors** 集合中。**Errors** 集合中编号最高的对象 (DBEngine.Errors.Count - 1) 对应于由 Microsoft Visual Basic for Applications (VBA) 的 **Err** 对象报告的错误。</span><span class="sxs-lookup"><span data-stu-id="68aba-p101">Any operation involving DAO objects can generate one or more errors. As each error occurs, one or more **Error** objects are placed in the **Errors** collection of the **DBEngine** object. When another DAO operation generates an error, the **Errors** collection is cleared, and the new set of **Error** objects is placed in the **Errors** collection. The highest-numbered object in the **Errors** collection (DBEngine.Errors.Count - 1) corresponds to the error reported by the Microsoft Visual Basic for Applications (VBA) **Err** object.</span></span>

<span data-ttu-id="68aba-110">不生成错误的 DAO 操作对 **Errors** 集合没有影响。</span><span class="sxs-lookup"><span data-stu-id="68aba-110">DAO operations that don't generate an error have no effect on the **Errors** collection.</span></span>

<span data-ttu-id="68aba-111">与其他集合的通常做法不同， **Errors** 集合中不会追加元素，因此 **Errors** 集合不支持 **Append** 和 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="68aba-111">Elements of the **Errors** collection aren't appended as they typically are with other collections, so the **Errors** collection doesn't support the **Append** and **Delete** methods.</span></span>

<span data-ttu-id="68aba-p102">**Errors** 集合中的 **Error** 对象集描述一个错误。第一个 **Error** 对象是最低级别的错误，第二个对象是更高一个级别的错误，依此类推。例如，如果在尝试打开 **[Recordset](recordset-object-dao.md)** 对象时发生了 ODBC 错误，则第一个错误对象包含最低级别的 ODBC 错误；随后的错误包含由 ODBC 的各个层返回的 ODBC 错误。在这种情况下，ODBC 驱动程序管理器（且有可能是驱动程序本身）将返回不同的 **Error** 对象。最后一个 **Error** 对象包含 DAO 错误，该错误指示无法打开对象。</span><span class="sxs-lookup"><span data-stu-id="68aba-p102">The set of **Error** objects in the **Errors** collection describes one error. The first **Error** object is the lowest level error, the second the next higher level, and so forth. For example, if an ODBC error occurs while trying to open a **[Recordset](recordset-object-dao.md)** object, the first error object contains the lowest level ODBC error; subsequent errors contain the ODBC errors returned by the various layers of ODBC. In this case, the ODBC driver manager, and possibly the driver itself, return separate **Error** objects. The last **Error** object contains the DAO error indicating that the object couldn't be opened.</span></span>

<span data-ttu-id="68aba-117">通过枚举 **Errors** 集合中的特定错误，您的错误处理例程可以更精确地确定错误的原因和根源，并采取相应的步骤进行恢复。</span><span class="sxs-lookup"><span data-stu-id="68aba-117">Enumerating the specific errors in the **Errors** collection enables your error-handling routines to more precisely determine the cause and origin of an error, and take appropriate steps to recover.</span></span>


> [!NOTE]
> <span data-ttu-id="68aba-p103">[!注释] 如果使用 **New** 关键字创建的对象会在放入 **Errors** 集合之前或在放入的过程中导致一个错误，则集合不会包含有关该对象的错误信息，因为新对象并不与 **DBEngine** 对象关联。但是，VBA **Err** 对象中包含错误信息。</span><span class="sxs-lookup"><span data-stu-id="68aba-p103">If you use the **New** keyword to create an object that causes an error either before or while being placed into the **Errors** collection, the collection doesn't contain error information about that object, because the new object is not associated with the **DBEngine** object. However, the error information is available in the VBA **Err** object.</span></span>

## <a name="example"></a><span data-ttu-id="68aba-120">示例</span><span class="sxs-lookup"><span data-stu-id="68aba-120">Example</span></span>

<span data-ttu-id="68aba-121">以下示例强制生成一个错误，然后捕获错误，并显示生成的 **Error** 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。</span><span class="sxs-lookup"><span data-stu-id="68aba-121">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting **Error** object.</span></span>

```vb 
Sub DescriptionX() 
 
 Dim dbsTest As Database 
 
 On Error GoTo ErrorHandler 
 
 ' Intentionally trigger an error. 
 Set dbsTest = OpenDatabase("NoDatabase") 
 
 Exit Sub 
 
ErrorHandler: 
 Dim strError As String 
 Dim errLoop As Error 
 
 ' Enumerate Errors collection and display properties of 
 ' each Error object. 
 For Each errLoop In Errors 
 With errLoop 
 strError = _ 
 "Error #" & .Number & vbCr 
 strError = strError & _ 
 " " & .Description & vbCr 
 strError = strError & _ 
 " (Source: " & .Source & ")" & vbCr 
 strError = strError & _ 
 "Press F1 to see topic " & .HelpContext & vbCr 
 strError = strError & _ 
 " in the file " & .HelpFile & "." 
 End With 
 MsgBox strError 
 Next 
 
 Resume Next 
 
End Sub 
 
```

