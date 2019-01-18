---
title: Error.Description 属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 1d7e949771e764c22e93ef56059930ccf39584ab
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28714561"
---
# <a name="errordescription-property-dao"></a><span data-ttu-id="8b036-102">Error.Description 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8b036-102">Error.Description property (DAO)</span></span>


<span data-ttu-id="8b036-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b036-103">**Applies to**: Access 2013, Office 2013</span></span>
 

<span data-ttu-id="8b036-p101">返回与某个错误关联的描述性字符串。这是 **Error** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="8b036-p101">Returns a descriptive string associated with an error. This is the default property for the **Error** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b036-106">语法</span><span class="sxs-lookup"><span data-stu-id="8b036-106">Syntax</span></span>

<span data-ttu-id="8b036-107">*表达式*。说明</span><span class="sxs-lookup"><span data-stu-id="8b036-107">*expression* .Description</span></span>

<span data-ttu-id="8b036-108">*表达式*一个代表**Error**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8b036-108">*expression* A variable that represents an **Error** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b036-109">注解</span><span class="sxs-lookup"><span data-stu-id="8b036-109">Remarks</span></span>

<span data-ttu-id="8b036-p102">**Description** 属性包括错误的简短说明。对于您无法处理或不希望处理的错误，可以使用该属性向用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="8b036-p102">The **Description** property comprises a short description of the error. Use this property to alert the user about an error that you cannot or do not want to handle.</span></span>

## <a name="example"></a><span data-ttu-id="8b036-112">示例</span><span class="sxs-lookup"><span data-stu-id="8b036-112">Example</span></span>

<span data-ttu-id="8b036-113">以下示例强制生成一个错误，然后捕获错误，并显示生成的 Error 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。</span><span class="sxs-lookup"><span data-stu-id="8b036-113">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting Error object.</span></span>

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

