---
title: Recordset.Requery Method (DAO)
TOCTitle: Requery Method
ms:assetid: a5d66eb5-499c-4133-f6c3-c7a1619a8a11
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821155(v=office.15)
ms:contentKeyID: 48546840
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 420ed0f95b283d7d50b4e50ca05c7dfca94a1390
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868474"
---
# <a name="recordsetrequery-method-dao"></a><span data-ttu-id="4d282-102">Recordset.Requery Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="4d282-102">Recordset.Requery Method (DAO)</span></span>


<span data-ttu-id="4d282-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d282-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4d282-104">通过重新执行对象所基于的查询，更新 **[Recordset](recordset-object-dao.md)** 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="4d282-104">Updates the data in a **[Recordset](recordset-object-dao.md)** object by re-executing the query on which the object is based.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d282-105">语法</span><span class="sxs-lookup"><span data-stu-id="4d282-105">Syntax</span></span>

<span data-ttu-id="4d282-106">*表达式*。Requery (***NewQueryDef***)</span><span class="sxs-lookup"><span data-stu-id="4d282-106">*expression* .Requery(***NewQueryDef***)</span></span>

<span data-ttu-id="4d282-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4d282-107">*expression* A variable that represents a **Recordset** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="4d282-108">参数</span><span class="sxs-lookup"><span data-stu-id="4d282-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4d282-109">名称</span><span class="sxs-lookup"><span data-stu-id="4d282-109">Name</span></span></p></th>
<th><p><span data-ttu-id="4d282-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="4d282-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="4d282-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="4d282-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="4d282-112">说明</span><span class="sxs-lookup"><span data-stu-id="4d282-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d282-113">NewQueryDef</span><span class="sxs-lookup"><span data-stu-id="4d282-113">NewQueryDef</span></span></p></td>
<td><p><span data-ttu-id="4d282-114">可选</span><span class="sxs-lookup"><span data-stu-id="4d282-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="4d282-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="4d282-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="4d282-116">表示 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象的 <strong>Name</strong> 属性值</span><span class="sxs-lookup"><span data-stu-id="4d282-116">Represents the <strong>Name</strong> property value of a <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4d282-117">注解</span><span class="sxs-lookup"><span data-stu-id="4d282-117">Remarks</span></span>

<span data-ttu-id="4d282-118">使用此方法可确保 **Recordset** 包含最新的数据。</span><span class="sxs-lookup"><span data-stu-id="4d282-118">Use this method to make sure that a **Recordset** contains the most recent data.</span></span> <span data-ttu-id="4d282-119">此方法重新填充当前**Recordset**使用当前查询参数或由 newquerydef 参数提供新的 （在 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="4d282-119">This method re-populates the current **Recordset** by using either the current query parameters or (in a Microsoft Access workspace) the new ones supplied by the newquerydef argument.</span></span>

<span data-ttu-id="4d282-120">如果不指定 newquerydef 参数， **Recordset**重新填充基于相同的查询定义和使用最初填充**Recordset**的参数。</span><span class="sxs-lookup"><span data-stu-id="4d282-120">If you don't specify a newquerydef argument, the **Recordset** is re-populated based on the same query definition and parameters used to originally populate the **Recordset**.</span></span> <span data-ttu-id="4d282-121">在此重新填充期间，将反映对基础数据所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="4d282-121">Any changes to the underlying data will be reflected during this re-population.</span></span> <span data-ttu-id="4d282-122">如果没有使用 **QueryDef** 创建 **Recordset**，将从头重新创建 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="4d282-122">If you didn't use a **QueryDef** to create the **Recordset**, the **Recordset** is re-created from scratch.</span></span>

<span data-ttu-id="4d282-123">如果 newquerydef 参数中指定原始**QueryDef** ， **Recordset**被重新使用指定的**QueryDef**的参数。</span><span class="sxs-lookup"><span data-stu-id="4d282-123">If you specify the original **QueryDef** in the newquerydef argument, then the **Recordset** is requeried using the parameters specified by the **QueryDef**.</span></span> <span data-ttu-id="4d282-124">在此重新填充期间，将反映对基础数据所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="4d282-124">Any changes to the underlying data will be reflected during this re-population.</span></span> <span data-ttu-id="4d282-125">以反映对**Recordset**中的查询参数值的任何更改，必须提供 newquerydef 的参数。</span><span class="sxs-lookup"><span data-stu-id="4d282-125">To reflect any changes to the query parameter values in the **Recordset**, you must supply the newquerydef argument.</span></span>

<span data-ttu-id="4d282-126">如果指定的与最初用来创建 **Recordset** 的 **QueryDef** 不相同，将从头重新创建 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="4d282-126">If you specify a different **QueryDef** than what was originally used to create the **Recordset**, the **Recordset** is re-created from scratch.</span></span>

<span data-ttu-id="4d282-127">如果使用 **Requery**， **Recordset** 中的第一条记录将成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="4d282-127">When you use **Requery**, the first record in the **Recordset** becomes the current record.</span></span>

<span data-ttu-id="4d282-128">不能对 \*\*\*\*Restartable\*\*\*\* 属性设置为 [False](recordset-restartable-property-dao.md) 的动态集类型或快照类型的 **Recordset** 对象使用 **Requery** 方法。</span><span class="sxs-lookup"><span data-stu-id="4d282-128">You can't use the **Requery** method on dynaset- or snapshot-type **Recordset** objects whose **[Restartable](recordset-restartable-property-dao.md)** property is set to **False**.</span></span> <span data-ttu-id="4d282-129">但是，如果您提供可选 newquerydef 参数，**一个可重启**属性将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4d282-129">However, if you supply the optional newquerydef argument, the **Restartable** property is ignored.</span></span>

<span data-ttu-id="4d282-130">使用 [Requery](recordset-bof-property-dao.md) 方法后，如果 **Recordset** 对象的 **[BOF](recordset-eof-property-dao.md)** 和 \*\*\*\*EOF\*\*\*\* 属性设置均为 **True**，则表示查询没有返回任何记录，并且 **Recordset** 不包含数据。</span><span class="sxs-lookup"><span data-stu-id="4d282-130">If both the **[BOF](recordset-bof-property-dao.md)** and **[EOF](recordset-eof-property-dao.md)** property settings of the **Recordset** object are **True** after you use the **Requery** method, the query didn't return any records and the **Recordset** contains no data.</span></span>

## <a name="example"></a><span data-ttu-id="4d282-131">示例</span><span class="sxs-lookup"><span data-stu-id="4d282-131">Example</span></span>

<span data-ttu-id="4d282-132">以下示例演示如何在更改基础数据之后，使用 **Requery** 方法刷新查询。</span><span class="sxs-lookup"><span data-stu-id="4d282-132">This example shows how the **Requery** method can be used to refresh a query after underlying data has been changed.</span></span>

```vb
    Sub RequeryX() 
     
     Dim dbsNorthwind As Database 
     Dim qdfTemp As QueryDef 
     Dim rstView As Recordset 
     Dim rstChange As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set qdfTemp = dbsNorthwind.CreateQueryDef("", _ 
     "PARAMETERS ViewCountry Text; " & _ 
     "SELECT FirstName, LastName, Country FROM " & _ 
     "Employees WHERE Country = [ViewCountry] " & _ 
     "ORDER BY LastName") 
     
     qdfTemp.Parameters!ViewCountry = "USA" 
     Debug.Print "Data after initial query, " & _ 
     [ViewCountry] = USA" 
     Set rstView = qdfTemp.OpenRecordset 
     Do While Not rstView.EOF 
     Debug.Print " " & rstView!FirstName & " " & _ 
     rstView!LastName & ", " & rstView!Country 
     rstView.MoveNext 
     Loop 
     
     ' Change underlying data. 
     Set rstChange = dbsNorthwind.OpenRecordset("Employees") 
     rstChange.AddNew 
     rstChange!FirstName = "Nina" 
     rstChange!LastName = "Roberts" 
     rstChange!Country = "USA" 
     rstChange.Update 
     
     rstView.Requery 
     Debug.Print "Requery after changing underlying data" 
     Set rstView = qdfTemp.OpenRecordset 
     Do While Not rstView.EOF 
     Debug.Print " " & rstView!FirstName & " " & _ 
     rstView!LastName & ", " & rstView!Country 
     rstView.MoveNext 
     Loop 
     
     ' Restore original data because this is only a 
     ' demonstration. 
     rstChange.Bookmark = rstChange.LastModified 
     rstChange.Delete 
     rstChange.Close 
     
     rstView.Close 
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="4d282-133">以下示例演示如何在更改查询参数后，使用 **Requery** 方法刷新查询。</span><span class="sxs-lookup"><span data-stu-id="4d282-133">This example shows how the **Requery** method can be used to refresh a query after the query parameters have been changed.</span></span>

```vb 
Sub RequeryX2() 
 
 Dim dbsNorthwind As Database 
 Dim qdfTemp As QueryDef 
 Dim prmCountry As Parameter 
 Dim rstView As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 Set qdfTemp = dbsNorthwind.CreateQueryDef("", _ 
 "PARAMETERS ViewCountry Text; " & _ 
 "SELECT FirstName, LastName, Country FROM " & _ 
 "Employees WHERE Country = [ViewCountry] " & _ 
 "ORDER BY LastName") 
 Set prmCountry = qdfTemp.Parameters!ViewCountry 
 
 qdfTemp.Parameters!ViewCountry = "USA" 
 Debug.Print "Data after initial query, " & _ 
 [ViewCountry] = USA" 
 Set rstView = qdfTemp.OpenRecordset 
 Do While Not rstView.EOF 
 Debug.Print " " & rstView!FirstName & " " & _ 
 rstView!LastName & ", " & rstView!Country 
 rstView.MoveNext 
 Loop 
 
 ' Change query parameter. 
 qdfTemp.Parameters!ViewCountry = "UK" 
 ' QueryDef argument must be included so that the 
 ' resulting Recordset reflects the change in the query 
 ' parameter. 
 rstView.Requery qdfTemp 
 Debug.Print "Requery after changing parameter, " & _ 
 "[ViewCountry] = UK" 
 Do While Not rstView.EOF 
 Debug.Print " " & rstView!FirstName & " " & _ 
 rstView!LastName & ", " & rstView!Country 
 rstView.MoveNext 
 Loop 
 
 rstView.Close 
 dbsNorthwind.Close 
 
End Sub 
 
```

