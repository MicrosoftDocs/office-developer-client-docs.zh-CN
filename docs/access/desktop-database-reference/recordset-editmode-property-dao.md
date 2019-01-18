---
title: Recordset.EditMode 属性 (DAO)
TOCTitle: EditMode Property
ms:assetid: 3cf67f64-c8c3-ad0a-ce00-6f37a3c264ee
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192697(v=office.15)
ms:contentKeyID: 48544329
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 326f23f95f9ccf8763f76b21df8955c39198a88c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718642"
---
# <a name="recordseteditmode-property-dao"></a><span data-ttu-id="4c09b-102">Recordset.EditMode 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4c09b-102">Recordset.EditMode property (DAO)</span></span>


<span data-ttu-id="4c09b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4c09b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4c09b-104">返回一个值，该值指示当前记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="4c09b-104">Returns a value that indicates the state of editing for the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c09b-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c09b-105">Syntax</span></span>

<span data-ttu-id="4c09b-106">*表达式*。EditMode</span><span class="sxs-lookup"><span data-stu-id="4c09b-106">*expression* .EditMode</span></span>

<span data-ttu-id="4c09b-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4c09b-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c09b-108">注解</span><span class="sxs-lookup"><span data-stu-id="4c09b-108">Remarks</span></span>

<span data-ttu-id="4c09b-p101">返回值是一个 **Long**，用于指示编辑的状态。该值可以是 **[EditModeEnum](editmodeenum-enumeration-dao.md)** 常量之一。</span><span class="sxs-lookup"><span data-stu-id="4c09b-p101">The return value is a **Long** that indicates the state of editing. The value can be one of the **[EditModeEnum](editmodeenum-enumeration-dao.md)** constants.</span></span>

<span data-ttu-id="4c09b-p102">例如，在验证过程中，如果由于错误中断了编辑过程，则 **EditMode** 属性十分有用。可以使用 **EditMode** 属性值确定应使用 **[Update](recordset-update-method-dao.md)** 方法还是 **[CancelUpdate](recordset-cancelupdate-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="4c09b-p102">The **EditMode** property is useful when an editing process is interrupted, for example, by an error during validation. You can use the value of the **EditMode** property to determine whether you should use the **[Update](recordset-update-method-dao.md)** or **[CancelUpdate](recordset-cancelupdate-method-dao.md)** method.</span></span>

<span data-ttu-id="4c09b-113">您也可以查看 **[LockEdits](recordset-lockedits-property-dao.md)** 属性设置是否为 **True** 以及 **EditMode** 属性设置是否为 **dbEditInProgress**，以确定当前页是否已被锁定。</span><span class="sxs-lookup"><span data-stu-id="4c09b-113">You can also check to see if the **[LockEdits](recordset-lockedits-property-dao.md)** property setting is **True** and the **EditMode** property setting is **dbEditInProgress** to determine whether the current page is locked.</span></span>

## <a name="example"></a><span data-ttu-id="4c09b-114">示例</span><span class="sxs-lookup"><span data-stu-id="4c09b-114">Example</span></span>

<span data-ttu-id="4c09b-p103">以下示例演示在各种情况下 **EditMode** 属性的值。若要运行此过程，必须使用 EditModeOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="4c09b-p103">This example shows the value of the **EditMode** property under various conditions. The EditModeOutput function is required for this procedure to run.</span></span>

```vb
    Sub EditModeX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     
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
