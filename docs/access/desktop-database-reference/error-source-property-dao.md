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
ms.openlocfilehash: 16d043f1906744988af35708a954e9224256f8f7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867991"
---
# <a name="errorsource-property-dao"></a><span data-ttu-id="af078-102">Error.Source Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="af078-102">Error.Source Property (DAO)</span></span>


<span data-ttu-id="af078-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="af078-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="af078-104">返回最初生成错误的对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="af078-104">Returns the name of the object or application that originally generated the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="af078-105">语法</span><span class="sxs-lookup"><span data-stu-id="af078-105">Syntax</span></span>

<span data-ttu-id="af078-106">*表达式*。源</span><span class="sxs-lookup"><span data-stu-id="af078-106">*expression* .Source</span></span>

<span data-ttu-id="af078-107">*表达式*一个代表**Error**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="af078-107">*expression* A variable that represents an **Error** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="af078-108">注解</span><span class="sxs-lookup"><span data-stu-id="af078-108">Remarks</span></span>

<span data-ttu-id="af078-p101">**Source** 属性值通常为对象的类名称或程序 ID。在代码无法处理另一个应用程序中的对象生成的错误时，使用 **Source** 属性可以向用户提供信息。</span><span class="sxs-lookup"><span data-stu-id="af078-p101">The **Source** property value is usually the object's class name or programmatic ID. Use the **Source** property to provide your users with information when your code is unable to handle an error generated in an object in another application.</span></span>

<span data-ttu-id="af078-111">例如，如果访问 Microsoft Excel，它将生成一个"被零除"错误，Microsoft Excel 将**Error.Number**设置为该错误的 Microsoft Excel 代码，并将**Source**属性设置为 Excel.Application。</span><span class="sxs-lookup"><span data-stu-id="af078-111">For example, if you access Microsoft Excel and it generates a "Division by zero" error, Microsoft Excel sets **Error.Number** to the Microsoft Excel code for that error and sets the **Source** property to Excel.Application.</span></span> <span data-ttu-id="af078-112">请注意，如果错误是在 Microsoft Excel 调用的另一个对象中生成的，Microsoft Excel 会截获该错误，并仍将 **Error.Number** 设置为 Microsoft Excel 代码。</span><span class="sxs-lookup"><span data-stu-id="af078-112">Note that if the error is generated in another object called by Microsoft Excel, Microsoft Excel intercepts the error and still sets **Error.Number** to the Microsoft Excel code.</span></span> <span data-ttu-id="af078-113">但是，其他 **Error** 对象属性（包括 **Source**）将保留生成错误的对象所设置的值。</span><span class="sxs-lookup"><span data-stu-id="af078-113">However, the other **Error** object properties (including **Source**) will retain the values as set by the object that generated the error.</span></span> <span data-ttu-id="af078-114">**Source** 属性始终包含最初生成错误的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="af078-114">The **Source** property always contains the name of the object that originally generated the error.</span></span>

<span data-ttu-id="af078-p103">您可以基于所有错误文档，编写相应处理错误的代码。如果您的错误处理程序失败，可以使用 **[Error](error-object-dao.md)** 对象信息向用户描述错误，使用 **Source** 属性和其他 **Error** 属性向用户提供有关最初导致错误的对象、错误的说明等等的信息。</span><span class="sxs-lookup"><span data-stu-id="af078-p103">Based on all of the error documentation, you can write code that will handle the error appropriately. If your error handler fails, you can use the **[Error](error-object-dao.md)** object information to describe the error to your user, using the **Source** property and the other **Error** properties to give the user information about which object originally caused the error, the description of the error, and so forth.</span></span>


> [!NOTE]
> <span data-ttu-id="af078-p104">在处理访问其他对象的过程中生成的错误时，最好使用 **On Error Resume Next** 结构，而不使用 **On Error GoTo**。如果在每次与对象交互后检查 **Error** 对象属性，可以清楚地了解发生错误时代码正在访问的对象。因此，您可以确定哪个对象在 **Error.Number** 中放置了错误代码，以及最初生成此错误的是哪个对象 (**Error.Source**)。</span><span class="sxs-lookup"><span data-stu-id="af078-p104">The **On Error Resume Next** construct may be preferable to **On Error GoTo** when dealing with errors generated during access to other objects. Checking the **Error** object property after each interaction with an object removes ambiguity about which object your code was accessing when the error occurred. Thus, you can be sure which object placed the error code in **Error.Number**, as well as which object originally generated the error (**Error.Source**).</span></span>

## <a name="example"></a><span data-ttu-id="af078-120">示例</span><span class="sxs-lookup"><span data-stu-id="af078-120">Example</span></span>

<span data-ttu-id="af078-121">以下示例强制生成一个错误，然后捕获错误，并显示生成的 **Error** 对象的 **Description**、 **Number**、 **Source**、 **HelpContext** 和 **HelpFile** 属性。</span><span class="sxs-lookup"><span data-stu-id="af078-121">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting **Error** object.</span></span>

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
