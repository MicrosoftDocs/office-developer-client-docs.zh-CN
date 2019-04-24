---
title: Errors 集合 (DAO)
TOCTitle: Errors Collection
ms:assetid: d42007b5-6410-14e9-baf9-9306fdef38f9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834805(v=office.15)
ms:contentKeyID: 48547929
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cf8e891936d4f8bd03535fa199026bc4ad8ff9ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293411"
---
# <a name="errors-collection-dao"></a>Errors 集合 (DAO)


**适用于**：Access 2013、Office 2013

**Errors** 集合包含所有存储的 **Error** 对象，这些对象中的每一个都与一个涉及 DAO 的操作有关。

## <a name="remarks"></a>注解

任何涉及 DAO 对象的操作都可以生成一个或多个错误。 每个错误发生时，系统会将一个或多个 **Error** 对象放在 **DBEngine** 对象的 **Errors** 集合中。 当另一个 DAO 操作生成错误时，将清除 **Errors** 集合，并将一组新的 **Error** 对象放在 **Errors** 集合中。 **Errors** 集合中编号最高的对象 (DBEngine.Errors.Count - 1) 对应于由 Microsoft Visual Basic for Applications (VBA) 的 **Err** 对象报告的错误。

不生成错误的 DAO 操作对 **Errors** 集合没有影响。

与其他集合的通常做法不同， **Errors** 集合中不会追加元素，因此 **Errors** 集合不支持 **Append** 和 **Delete** 方法。

**Errors** 集合中的 **Error** 对象集描述一个错误。第一个 **Error** 对象是最低级别的错误，第二个对象是更高一个级别的错误，依此类推。例如，如果在尝试打开 **[Recordset](recordset-object-dao.md)** 对象时发生了 ODBC 错误，则第一个错误对象包含最低级别的 ODBC 错误；随后的错误包含由 ODBC 的各个层返回的 ODBC 错误。在这种情况下，ODBC 驱动程序管理器（且有可能是驱动程序本身）将返回不同的 **Error** 对象。最后一个 **Error** 对象包含 DAO 错误，该错误指示无法打开对象。

通过枚举 **Errors** 集合中的特定错误，您的错误处理例程可以更精确地确定错误的原因和根源，并采取相应的步骤进行恢复。


> [!NOTE]
> [!注释] 如果使用 **New** 关键字创建的对象会在放入 **Errors** 集合之前或在放入的过程中导致一个错误，则集合不会包含有关该对象的错误信息，因为新对象并不与 **DBEngine** 对象关联。但是，VBA **Err** 对象中包含错误信息。

## <a name="example"></a>示例

以下示例强制生成一个错误，然后捕获错误，并显示生成的 **Error** 对象的 **Description**、**Number**、**Source**、**HelpContext** 和 **HelpFile** 属性。

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

