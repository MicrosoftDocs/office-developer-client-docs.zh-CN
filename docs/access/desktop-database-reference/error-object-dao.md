---
title: Error 对象的数据访问对象 (DAO)
TOCTitle: Error Object
ms:assetid: e2608bc9-bece-9b47-4562-7a2689601f75
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835711(v=office.15)
ms:contentKeyID: 48548289
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4a42fdf47b736b13cea53122431606224d2f9da
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889558"
---
# <a name="error-object-dao"></a>Error Object (DAO)


**适用于**： Access 2013、 Office 2013

**Error** 对象包含有关数据访问错误的详细信息，其中每种错误都关系到与 DAO 有关的单个操作。

## <a name="remarks"></a>注解

与 DAO 有关的任何操作都可能会产生一个或多个错误。例如，调用 ODBC 服务器可能导致来自数据库服务器的错误、来自 ODBC 的错误和 DAO 错误。每次发生这种错误时， **Error** 对象都会被放入到 **DBEngine** 对象的 **Errors** 集合中。因此，单个事件可能导致 **Errors** 集合中出现多个 **Error** 对象。

如果后续的 DAO 操作产生了错误，将会清除 **Errors** 集合，同时将一个或多个新的 **Error** 对象放入 **Errors** 集合中。不生成错误的 DAO 操作对 **Errors** 集合没有影响。

**Errors** 集合中的 **Error** 对象集描述一个错误。第一个 **Error** 对象是最低级别的错误（始发错误），第二个为高一个级别的错误，以此类推。例如，如果在尝试打开某个 **[Recordset](recordset-object-dao.md)** 对象时发生 ODBC 错误，则第一个 **Error** 对象（即 **Errors**(0)）包含最低级别的 ODBC 错误；后续错误包含 ODBC 各个层返回的 ODBC 错误。在这种情况下，ODBC 驱动程序管理器（且有可能是驱动程序本身）将返回不同的 **Error** 对象。最后一个 **Error** 对象（即 **Errors.Count-** 1）包含指示无法打开该对象的 DAO 错误。

通过枚举 **Errors** 集合中的特定错误，您的错误处理例程可以更精确地确定错误的原因和根源，并采取相应的步骤进行恢复。可以通过了解 **Error** 对象的属性来获取与每个错误有关的特定详细信息，包括：

  - **[Description](error-description-property-dao.md)** 属性，包含在没有捕获到错误的情况下显示在屏幕上的错误警告的文本。

  - **[Number](error-number-property-dao.md)** 属性，包含错误常量的 Long 类型整数值。

  - **[Source](error-source-property-dao.md)** 属性，标识引发错误的对象。在对 ODBC 数据源发出请求后，如果 **Errors** 集合中包括多个 **Error** 对象，则使用该属性尤其有用。

  - **HelpFile** 和 **HelpContext** 属性，分别指示与错误对应的 Microsoft Windows 帮助文件和帮助主题（如果存在）。
    

    > [!NOTE]
    > [!注释] 在 Microsoft Visual Basic for Applications (VBA) 中编程时，如果使用 **New** 关键字创建了一个对象，并且以后该对象被追加到集合之前会导致出错，那么 **DBEngine** 对象的 **Errors** 集合将不包含该对象的错误的项，因为新对象与 **DBEngine** 对象不关联。 但是，VBA **Err** 对象中包含错误信息。 只要您预计可能存在数据访问错误，就应使 VBA 错误处理代码检查 **Errors** 集合。 在编写集中式错误处理程序时，应测试 VBA **Err** 对象，以确定 **Errors** 集合中的错误信息是否有效。 如果**Errors**集合 (DBEngine.Errors.Count-1) 的最后一个元素的**编号**属性和**Err**对象匹配的值，然后可以使用一系列**Select Case**语句来标识的特定的 DAO 错误或发生的错误。 如果两者不匹配，请对 [Errors](errors-refresh-method-dao.md) 集合使用 **Refresh** 方法。



## <a name="example"></a>示例

以下示例强制生成一个错误，然后捕获错误，并显示生成的 **Error** 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。

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
            "  " & .Description & vbCr 
         strError = strError & _ 
            "  (Source: " & .Source & ")" & vbCr 
         strError = strError & _ 
            "Press F1 to see topic " & .HelpContext & vbCr 
         strError = strError & _ 
            "  in the file " & .HelpFile & "." 
      End With 
      MsgBox strError 
   Next 
 
   Resume Next 
 
End Sub 
 
```

