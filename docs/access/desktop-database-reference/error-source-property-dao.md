---
title: Error.Source Property (DAO)
TOCTitle: Source Property
ms:assetid: 3c101cac-278e-025e-55a4-8a9d1ee7db3c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192677(v=office.15)
ms:contentKeyID: 48544302
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053360
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b9aafe1b16b3d989a81ff21f97bd4b6d10f79de3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467792"
---
# <a name="errorsource-property-dao"></a>Error.Source Property (DAO)


**适用于**： Access 2013 |Office 2013


返回最初生成错误的对象或应用程序的名称。

## <a name="syntax"></a>语法

*表达式*。源

*表达式*一个代表**Error**对象的变量。

## <a name="remarks"></a>注解

**Source** 属性值通常为对象的类名称或程序 ID。在代码无法处理另一个应用程序中的对象生成的错误时，使用 **Source** 属性可以向用户提供信息。

例如，如果访问 Microsoft Excel，它将生成一个"被零除"错误，Microsoft Excel 将**Error.Number**设置为该错误的 Microsoft Excel 代码，并将**Source**属性设置为 Excel.Application。 请注意，如果错误是在 Microsoft Excel 调用的另一个对象中生成的，Microsoft Excel 会截获该错误，并仍将 **Error.Number** 设置为 Microsoft Excel 代码。 但是，其他 **Error** 对象属性（包括 **Source**）将保留生成错误的对象所设置的值。 **Source** 属性始终包含最初生成错误的对象的名称。

您可以基于所有错误文档，编写相应处理错误的代码。如果您的错误处理程序失败，可以使用 **[Error](error-object-dao.md)** 对象信息向用户描述错误，使用 **Source** 属性和其他 **Error** 属性向用户提供有关最初导致错误的对象、错误的说明等等的信息。


> [!NOTE]
> <P>在处理访问其他对象的过程中生成的错误时，最好使用 <STRONG>On Error Resume Next</STRONG> 结构，而不使用 <STRONG>On Error GoTo</STRONG>。如果在每次与对象交互后检查 <STRONG>Error</STRONG> 对象属性，可以清楚地了解发生错误时代码正在访问的对象。因此，您可以确定哪个对象在 <STRONG>Error.Number</STRONG> 中放置了错误代码，以及最初生成此错误的是哪个对象 (<STRONG>Error.Source</STRONG>)。</P>



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
