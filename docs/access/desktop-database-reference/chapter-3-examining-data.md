---
title: 第 3 章： 检查数据
TOCTitle: 'Chapter 3: Examining data'
ms:assetid: 73c69134-3127-3344-d5c3-5ecb9e0e958b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249474(v=office.15)
ms:contentKeyID: 48545648
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4b489400536675fccced8f87aae515b019b87123
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936859"
---
# <a name="chapter-3-examining-data"></a><span data-ttu-id="2bdb2-102">第 3 章： 检查数据</span><span class="sxs-lookup"><span data-stu-id="2bdb2-102">Chapter 3: Examining data</span></span>

<span data-ttu-id="2bdb2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2bdb2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2bdb2-p101">第 2 章介绍了如何从作为 **Recordset** 对象的数据源中检索数据。本章将更深入地讨论 **Recordset** ，包括如何在 **Recordset** 中导航并查看其中的数据。</span><span class="sxs-lookup"><span data-stu-id="2bdb2-p101">Chapter 2 explained how to retrieve data from a data source as a **Recordset** object. This chapter will discuss the **Recordset** in more detail, including how to navigate through the **Recordset** and view its data.</span></span>

<span data-ttu-id="2bdb2-p102">**Recordsets** 具有旨在便于浏览和查看其中内容的方法和属性。取决于提供程序支持的功能，某些 **Recordset** 方法或属性可能不可用。若要继续研究 **Recordset** 对象，请考虑将从 Microsoft SQL Server 2000 上的罗斯文示例数据库返回的 **Recordset** ，使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="2bdb2-p102">**Recordsets** have methods and properties designed to make it easy to move through them and examine their contents. Depending on the functionality supported by the provider, some **Recordset** methods or properties might not be available. To continue exploring the **Recordset** object, consider a **Recordset** that would be returned from the Northwind sample database on Microsoft SQL Server 2000, using the following code:</span></span>

```vb 
 
'BeginRsTour 
Public Sub RecordsetTour() 
 On Error GoTo ErrHandler: 
 
 Dim objRs As New ADODB.Recordset 
 Dim strSQL As String 
 
 strSQL = "SELECT ProductID, ProductName, UnitPrice FROM Products " & _ 
 "WHERE CategoryID = 7" '7 = Produce 
 
 objRs.Open strSQL, strConnStr, adOpenForwardOnly, _ 
 adLockReadOnly, adCmdText 
 
 'Clean up 
 objRs.Close 
 Set objRs = Nothing 
 Exit Sub 
 
ErrHandler: 
 If Not objRs Is Nothing Then 
 If objRs.State = adStateOpen Then objRs.Close 
 Set objRs = Nothing 
 End If 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndRsTour 
```

<br/>

<span data-ttu-id="2bdb2-p103">以下 SQL 查询返回一个具有五行（记录）和三列（字段）的 **Recordset** 。下表中显示了各行的值。</span><span class="sxs-lookup"><span data-stu-id="2bdb2-p103">This SQL query returns a **Recordset** with five rows (records) and three columns (fields). The values for each row are shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2bdb2-111">字段 0</span><span class="sxs-lookup"><span data-stu-id="2bdb2-111">FIELD 0</span></span><br />
<span data-ttu-id="2bdb2-112">名称 = 产品 Id</span><span class="sxs-lookup"><span data-stu-id="2bdb2-112">Name = ProductID</span></span></p></th>
<th><p><span data-ttu-id="2bdb2-113">字段 1</span><span class="sxs-lookup"><span data-stu-id="2bdb2-113">FIELD 1</span></span><br />
<span data-ttu-id="2bdb2-114">名称 = 产品名</span><span class="sxs-lookup"><span data-stu-id="2bdb2-114">Name = ProductName</span></span></p></th>
<th><p><span data-ttu-id="2bdb2-115">字段 2</span><span class="sxs-lookup"><span data-stu-id="2bdb2-115">FIELD 2</span></span><br />
<span data-ttu-id="2bdb2-116">名称 = 单价</span><span class="sxs-lookup"><span data-stu-id="2bdb2-116">Name = UnitPrice</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bdb2-117">7</span><span class="sxs-lookup"><span data-stu-id="2bdb2-117">7</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-118">海鲜粉</span><span class="sxs-lookup"><span data-stu-id="2bdb2-118">Uncle Bob's Organic Dried Pears</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-119">30.0000</span><span class="sxs-lookup"><span data-stu-id="2bdb2-119">30.0000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bdb2-120">14</span><span class="sxs-lookup"><span data-stu-id="2bdb2-120">14</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-121">沙茶</span><span class="sxs-lookup"><span data-stu-id="2bdb2-121">Tofu</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-122">23.2500</span><span class="sxs-lookup"><span data-stu-id="2bdb2-122">23.2500</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bdb2-123">28</span><span class="sxs-lookup"><span data-stu-id="2bdb2-123">28</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-124">烤肉酱</span><span class="sxs-lookup"><span data-stu-id="2bdb2-124">Rssle Sauerkraut</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-125">45.6000</span><span class="sxs-lookup"><span data-stu-id="2bdb2-125">45.6000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bdb2-126">51</span><span class="sxs-lookup"><span data-stu-id="2bdb2-126">51</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-127">猪肉干</span><span class="sxs-lookup"><span data-stu-id="2bdb2-127">Manjimup Dried Apples</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-128">53.0000</span><span class="sxs-lookup"><span data-stu-id="2bdb2-128">53.0000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bdb2-129">74</span><span class="sxs-lookup"><span data-stu-id="2bdb2-129">74</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-130">鸡精</span><span class="sxs-lookup"><span data-stu-id="2bdb2-130">Longlife Tofu</span></span></p></td>
<td><p><span data-ttu-id="2bdb2-131">10.0000</span><span class="sxs-lookup"><span data-stu-id="2bdb2-131">10.0000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2bdb2-132">下一节介绍如何在此示例**Recordset**中找到指针的当前位置。</span><span class="sxs-lookup"><span data-stu-id="2bdb2-132">The next section explains how to locate the current position of the cursor in this sample **Recordset**.</span></span>

<span data-ttu-id="2bdb2-133">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="2bdb2-133">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="2bdb2-134">定位当前记录 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2bdb2-134">Locating the current record (ADO)</span></span>](locating-the-current-record.md)
- [<span data-ttu-id="2bdb2-135">导航数据 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2bdb2-135">Navigating through the data (ADO)</span></span>](navigating-through-the-data.md)
- [<span data-ttu-id="2bdb2-136">了解记录集结构 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2bdb2-136">Understanding Recordset structure (ADO)</span></span>](understanding-recordset-structure.md)