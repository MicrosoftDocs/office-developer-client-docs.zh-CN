---
title: EditModeEnum (Access desktop database reference)
TOCTitle: EditModeEnum
ms:assetid: 4da0e504-aca2-b769-04a2-0df687fa4422
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249248(v=office.15)
ms:contentKeyID: 48544737
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 246d9e29f084efb975783fd15c15993eba5a6e74
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293579"
---
# <a name="editmodeenum"></a><span data-ttu-id="4470e-102">EditModeEnum</span><span class="sxs-lookup"><span data-stu-id="4470e-102">EditModeEnum</span></span>

<span data-ttu-id="4470e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4470e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4470e-104">指定记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="4470e-104">Specifies the editing status of a record.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4470e-105">常量</span><span class="sxs-lookup"><span data-stu-id="4470e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="4470e-106">值</span><span class="sxs-lookup"><span data-stu-id="4470e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="4470e-107">说明</span><span class="sxs-lookup"><span data-stu-id="4470e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4470e-108"><strong>adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="4470e-108"><strong>adEditNone</strong></span></span></p></td>
<td><p><span data-ttu-id="4470e-109">0</span><span class="sxs-lookup"><span data-stu-id="4470e-109">0</span></span></p></td>
<td><p><span data-ttu-id="4470e-110">指示没有正在进行的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="4470e-110">Indicates that no editing operation is in progress.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4470e-111"><strong>adEditInProgress</strong></span><span class="sxs-lookup"><span data-stu-id="4470e-111"><strong>adEditInProgress</strong></span></span></p></td>
<td><p><span data-ttu-id="4470e-112">1</span><span class="sxs-lookup"><span data-stu-id="4470e-112">1</span></span></p></td>
<td><p><span data-ttu-id="4470e-113">指示当前记录中的数据已经修改但未保存。</span><span class="sxs-lookup"><span data-stu-id="4470e-113">Indicates that data in the current record has been modified but not saved.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4470e-114"><strong>adEditAdd</strong></span><span class="sxs-lookup"><span data-stu-id="4470e-114"><strong>adEditAdd</strong></span></span></p></td>
<td><p><span data-ttu-id="4470e-115">双面</span><span class="sxs-lookup"><span data-stu-id="4470e-115">2</span></span></p></td>
<td><p><span data-ttu-id="4470e-116">指示已调用 <a href="addnew-method-ado.md">AddNew</a> 方法，且复制缓冲区中的当前记录是尚未保存在数据库中保存的新记录。</span><span class="sxs-lookup"><span data-stu-id="4470e-116">Indicates that the <a href="addnew-method-ado.md">AddNew</a> method has been called, and the current record in the copy buffer is a new record that has not been saved in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4470e-117"><strong>adEditDelete</strong></span><span class="sxs-lookup"><span data-stu-id="4470e-117"><strong>adEditDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="4470e-118">4</span><span class="sxs-lookup"><span data-stu-id="4470e-118">4</span></span></p></td>
<td><p><span data-ttu-id="4470e-119">指示已删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="4470e-119">Indicates that the current record has been deleted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="4470e-120">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="4470e-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="4470e-121">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="4470e-121">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4470e-122">常量</span><span class="sxs-lookup"><span data-stu-id="4470e-122">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4470e-123">AdoEnums EditMode</span><span class="sxs-lookup"><span data-stu-id="4470e-123">AdoEnums.EditMode.NONE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4470e-124">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="4470e-124">AdoEnums.EditMode.INPROGRESS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4470e-125">AdoEnums EditMode。</span><span class="sxs-lookup"><span data-stu-id="4470e-125">AdoEnums.EditMode.ADD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4470e-126">AdoEnums EditMode</span><span class="sxs-lookup"><span data-stu-id="4470e-126">AdoEnums.EditMode.DELETE</span></span></p></td>
</tr>
</tbody>
</table>

