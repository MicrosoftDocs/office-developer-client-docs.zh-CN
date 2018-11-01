---
title: Error.Description Property (DAO)
TOCTitle: Description Property
ms:assetid: 47a84bec-3258-f2c7-e1af-239da39844dc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193218(v=office.15)
ms:contentKeyID: 48544601
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053358
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2de4c87832956fb690f67f734d418a855b179d8c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870336"
---
# <a name="errordescription-property-dao"></a>Error.Description Property (DAO)


**适用于**： Access 2013、 Office 2013
 

返回与某个错误关联的描述性字符串。这是 **Error** 对象的默认属性。

## <a name="syntax"></a>语法

*表达式*。说明

*表达式*一个代表**Error**对象的变量。

## <a name="remarks"></a>注解

**Description** 属性包括错误的简短说明。对于您无法处理或不希望处理的错误，可以使用该属性向用户发出警报。

## <a name="example"></a>示例

以下示例强制生成一个错误，然后捕获错误，并显示生成的 Error 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。

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

