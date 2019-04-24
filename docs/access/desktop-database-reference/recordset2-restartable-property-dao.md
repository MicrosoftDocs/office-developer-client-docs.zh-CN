---
title: Recordset2 属性 (DAO)
TOCTitle: Restartable Property
ms:assetid: 9b1c40f8-5a33-2527-a7b6-bef4cb991d7e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198019(v=office.15)
ms:contentKeyID: 48546560
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 873911ff8475a0b37f3f67d9cb2c01afc577487d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309076"
---
# <a name="recordset2restartable-property-dao"></a><span data-ttu-id="b7850-102">Recordset2 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="b7850-102">Recordset2.Restartable property (DAO)</span></span>


<span data-ttu-id="b7850-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7850-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b7850-104">返回一个值，该值表示 **[Recordset](recordset-object-dao.md)** 对象是否支持 **[Requery](recordset2-requery-method-dao.md)** 方法，该方法重新执行 **Recordset** 对象所基于的查询。</span><span class="sxs-lookup"><span data-stu-id="b7850-104">Returns a value that indicates whether a **[Recordset](recordset-object-dao.md)** object supports the **[Requery](recordset2-requery-method-dao.md)** method, which re-executes the query on which the **Recordset** object is based.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7850-105">语法</span><span class="sxs-lookup"><span data-stu-id="b7850-105">Syntax</span></span>

<span data-ttu-id="b7850-106">*表达式*。合用</span><span class="sxs-lookup"><span data-stu-id="b7850-106">*expression* .Restartable</span></span>

<span data-ttu-id="b7850-107">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b7850-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7850-108">注解</span><span class="sxs-lookup"><span data-stu-id="b7850-108">Remarks</span></span>

<span data-ttu-id="b7850-109">表类型 **Recordset** 对象始终返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="b7850-109">Table-type **Recordset** objects always return **False**.</span></span>

<span data-ttu-id="b7850-p101">在对 **Recordset** 对象使用 **Requery** 方法之前，检查 **Restartable** 属性。如果该对象的 **Restartable** 属性设置为 **False**，则对基础 **[QueryDef](connection-openrecordset-method-dao.md)** 对象使用 **[OpenRecordset](querydef-object-dao.md)** 方法，以重新执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7850-p101">Check the **Restartable** property before using the **Requery** method on a **Recordset** object. If the object's **Restartable** property is set to **False**, use the **[OpenRecordset](connection-openrecordset-method-dao.md)** method on the underlying **[QueryDef](querydef-object-dao.md)** object to re-execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="b7850-112">示例</span><span class="sxs-lookup"><span data-stu-id="b7850-112">Example</span></span>

<span data-ttu-id="b7850-113">以下示例使用不同的 **Recordset** 对象演示 **Restartable** 属性。</span><span class="sxs-lookup"><span data-stu-id="b7850-113">This example demonstrates the **Restartable** property with different **Recordset** objects.</span></span>

```vb
    Sub RestartableX()
    
       Dim dbsNorthwind As Database
       Dim rstTemp As Recordset2
    
       Set dbsNorthwind = OpenDatabase("Northwind.mdb")
    
       With dbsNorthwind
          ' Open a table-type Recordset and print its 
          ' Restartable property.
          Set rstTemp = .OpenRecordset("Employees", dbOpenTable)
          Debug.Print _
             "Table-type recordset from Employees table"
          Debug.Print "  Restartable = " & rstTemp.Restartable
          rstTemp.Close
    
          ' Open a Recordset from an SQL statement and print its 
          ' Restartable property.
          Set rstTemp = _
             .OpenRecordset("SELECT * FROM Employees")
          Debug.Print "Recordset based on SQL statement"
          Debug.Print "  Restartable = " & rstTemp.Restartable
          rstTemp.Close
    
          ' Open a Recordset from a saved QueryDef object and 
          ' print its Restartable property.
          Set rstTemp = .OpenRecordset("Current Product List")
          Debug.Print _
             "Recordset based on permanent QueryDef (" & _
             rstTemp.Name & ")"
          Debug.Print "  Restartable = " & rstTemp.Restartable
          rstTemp.Close
    
          .Close
       End With
    
    End Sub
```
