---
title: Error.Number Property (DAO)
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
ms.openlocfilehash: 8e7f5f4b6a0d4fa12be35a20f0a17717fdef1062
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465982"
---
# <a name="errornumber-property-dao"></a><span data-ttu-id="bab97-102">Error.Number Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="bab97-102">Error.Number Property (DAO)</span></span>


<span data-ttu-id="bab97-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bab97-103">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="bab97-104">返回一个数字值，该值指定错误。</span><span class="sxs-lookup"><span data-stu-id="bab97-104">Returns a numeric value specifying an error.</span></span>

## <a name="syntax"></a><span data-ttu-id="bab97-105">语法</span><span class="sxs-lookup"><span data-stu-id="bab97-105">Syntax</span></span>

<span data-ttu-id="bab97-106">*表达式*。号码</span><span class="sxs-lookup"><span data-stu-id="bab97-106">*expression* .Number</span></span>

<span data-ttu-id="bab97-107">*表达式*一个代表**Error**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bab97-107">*expression* A variable that represents an **Error** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bab97-108">注解</span><span class="sxs-lookup"><span data-stu-id="bab97-108">Remarks</span></span>

<span data-ttu-id="bab97-p101">使用 **Number** 属性确定发生了哪种错误。该属性的值是与错误条件对应的唯一陷阱号。</span><span class="sxs-lookup"><span data-stu-id="bab97-p101">Use the **Number** property to determine the error that occurred. The value of the property corresponds to a unique trap number that corresponds to an error condition.</span></span>

## <a name="example"></a><span data-ttu-id="bab97-111">示例</span><span class="sxs-lookup"><span data-stu-id="bab97-111">Example</span></span>

<span data-ttu-id="bab97-112">以下示例强制生成一个错误，然后捕获错误，并显示生成的 **Error** 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。</span><span class="sxs-lookup"><span data-stu-id="bab97-112">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting **Error** object.</span></span>

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

