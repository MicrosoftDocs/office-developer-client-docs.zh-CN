---
title: Recordset2.Restartable Property (DAO)
TOCTitle: Restartable Property
ms:assetid: 9b1c40f8-5a33-2527-a7b6-bef4cb991d7e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198019(v=office.15)
ms:contentKeyID: 48546560
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3be986fce66342ec736ebfebcfbc3e615ae57a40
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467364"
---
# <a name="recordset2restartable-property-dao"></a><span data-ttu-id="6a214-102">Recordset2.Restartable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="6a214-102">Recordset2.Restartable Property (DAO)</span></span>


<span data-ttu-id="6a214-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6a214-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6a214-104">返回一个值，该值表示 **[Recordset](recordset-object-dao.md)** 对象是否支持 **[Requery](recordset2-requery-method-dao.md)** 方法，该方法重新执行 **Recordset** 对象所基于的查询。</span><span class="sxs-lookup"><span data-stu-id="6a214-104">Returns a value that indicates whether a **[Recordset](recordset-object-dao.md)** object supports the **[Requery](recordset2-requery-method-dao.md)** method, which re-executes the query on which the **Recordset** object is based.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a214-105">语法</span><span class="sxs-lookup"><span data-stu-id="6a214-105">Syntax</span></span>

<span data-ttu-id="6a214-106">*表达式*。可重新启动</span><span class="sxs-lookup"><span data-stu-id="6a214-106">*expression* .Restartable</span></span>

<span data-ttu-id="6a214-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6a214-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a214-108">注解</span><span class="sxs-lookup"><span data-stu-id="6a214-108">Remarks</span></span>

<span data-ttu-id="6a214-109">表类型 **Recordset** 对象始终返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="6a214-109">Table-type **Recordset** objects always return **False**.</span></span>

<span data-ttu-id="6a214-p101">在对 **Recordset** 对象使用 **Requery** 方法之前，检查 **Restartable** 属性。如果该对象的 **Restartable** 属性设置为 **False**，则对基础 **[QueryDef](connection-openrecordset-method-dao.md)** 对象使用 **[OpenRecordset](querydef-object-dao.md)** 方法，以重新执行查询。</span><span class="sxs-lookup"><span data-stu-id="6a214-p101">Check the **Restartable** property before using the **Requery** method on a **Recordset** object. If the object's **Restartable** property is set to **False**, use the **[OpenRecordset](connection-openrecordset-method-dao.md)** method on the underlying **[QueryDef](querydef-object-dao.md)** object to re-execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="6a214-112">示例</span><span class="sxs-lookup"><span data-stu-id="6a214-112">Example</span></span>

<span data-ttu-id="6a214-113">以下示例使用不同的 **Recordset** 对象演示 **Restartable** 属性。</span><span class="sxs-lookup"><span data-stu-id="6a214-113">This example demonstrates the **Restartable** property with different **Recordset** objects.</span></span>

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