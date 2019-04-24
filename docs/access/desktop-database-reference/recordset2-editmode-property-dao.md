---
title: EditMode 属性 (DAO) Recordset2
TOCTitle: EditMode Property
ms:assetid: fd61ea2b-e7d7-195f-4114-87e54eba2451
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837240(v=office.15)
ms:contentKeyID: 48548914
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053080
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: d4043a442bec8c5ce421d85de6256eb9c5cb353f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307348"
---
# <a name="recordset2editmode-property-dao"></a><span data-ttu-id="b411e-102">EditMode 属性 (DAO) Recordset2</span><span class="sxs-lookup"><span data-stu-id="b411e-102">Recordset2.EditMode property (DAO)</span></span>


<span data-ttu-id="b411e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b411e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b411e-104">返回一个值，该值指示当前记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="b411e-104">Returns a value that indicates the state of editing for the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="b411e-105">语法</span><span class="sxs-lookup"><span data-stu-id="b411e-105">Syntax</span></span>

<span data-ttu-id="b411e-106">*表达式*。EditMode</span><span class="sxs-lookup"><span data-stu-id="b411e-106">*expression* .EditMode</span></span>

<span data-ttu-id="b411e-107">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b411e-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b411e-108">注解</span><span class="sxs-lookup"><span data-stu-id="b411e-108">Remarks</span></span>

<span data-ttu-id="b411e-p101">返回值是一个 **Long**，用于指示编辑的状态。该值可以是 **[EditModeEnum](editmodeenum-enumeration-dao.md)** 常量之一。</span><span class="sxs-lookup"><span data-stu-id="b411e-p101">The return value is a **Long** that indicates the state of editing. The value can be one of the **[EditModeEnum](editmodeenum-enumeration-dao.md)** constants.</span></span>

<span data-ttu-id="b411e-p102">例如，在验证过程中，如果由于错误中断了编辑过程，则 **EditMode** 属性十分有用。可以使用 **EditMode** 属性值确定应使用 **[Update](recordset2-update-method-dao.md)** 方法还是 **[CancelUpdate](recordset2-cancelupdate-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="b411e-p102">The **EditMode** property is useful when an editing process is interrupted, for example, by an error during validation. You can use the value of the **EditMode** property to determine whether you should use the **[Update](recordset2-update-method-dao.md)** or **[CancelUpdate](recordset2-cancelupdate-method-dao.md)** method.</span></span>

<span data-ttu-id="b411e-113">您也可以查看 **[LockEdits](recordset2-lockedits-property-dao.md)** 属性设置是否为 **True** 以及 **EditMode** 属性设置是否为 **dbEditInProgress**，以确定当前页是否被锁定。</span><span class="sxs-lookup"><span data-stu-id="b411e-113">You can also check to see if the **[LockEdits](recordset2-lockedits-property-dao.md)** property setting is **True** and the **EditMode** property setting is **dbEditInProgress** to determine whether the current page is locked.</span></span>

## <a name="example"></a><span data-ttu-id="b411e-114">示例</span><span class="sxs-lookup"><span data-stu-id="b411e-114">Example</span></span>

<span data-ttu-id="b411e-p103">以下示例演示在各种情况下 **EditMode** 属性的值。若要运行此过程，必须使用 EditModeOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="b411e-p103">This example shows the value of the **EditMode** property under various conditions. The EditModeOutput function is required for this procedure to run.</span></span>

```vb
    Sub EditModeX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     ' Show the EditMode property under different editing 
     ' states. 
     With rstEmployees 
     EditModeOutput "Before any Edit or AddNew:", .EditMode 
     .Edit 
     EditModeOutput "After Edit:", .EditMode 
     .Update 
     EditModeOutput "After Update:", .EditMode 
     .AddNew 
     EditModeOutput "After AddNew:", .EditMode 
     .CancelUpdate 
     EditModeOutput "After CancelUpdate:", .EditMode 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function EditModeOutput(strTemp As String, _ 
     intEditMode As Integer) 
     
     ' Print report based on the value of the EditMode 
     ' property. 
     Debug.Print strTemp 
     Debug.Print " EditMode = "; 
     
     Select Case intEditMode 
     Case dbEditNone 
     Debug.Print "dbEditNone" 
     Case dbEditInProgress 
     Debug.Print "dbEditInProgress" 
     Case dbEditAdd 
     Debug.Print "dbEditAdd" 
     End Select 
     
    End Function
```
