---
title: 错误。 Number 属性 (DAO)
TOCTitle: Number Property
ms:assetid: 2fb94dca-f990-04f8-bbd2-9919d28de75a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192259(v=office.15)
ms:contentKeyID: 48544013
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053363
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 257c403951eff5bbb2f37de8b38a1c63a3445285
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293495"
---
# <a name="errornumber-property-dao"></a>错误。 Number 属性 (DAO)


**适用于**：Access 2013、Office 2013
 

返回一个数字值，该值指定错误。

## <a name="syntax"></a>语法

*表达式*。多种

*表达式*一个代表**Error**对象的变量。

## <a name="remarks"></a>注解

使用 **Number** 属性确定发生了哪种错误。该属性的值是与错误条件对应的唯一陷阱号。

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

