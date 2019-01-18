---
title: EditModeEnum （访问桌面数据库参考 （英文）
TOCTitle: EditModeEnum
ms:assetid: 4da0e504-aca2-b769-04a2-0df687fa4422
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249248(v=office.15)
ms:contentKeyID: 48544737
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 246d9e29f084efb975783fd15c15993eba5a6e74
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726286"
---
# <a name="editmodeenum"></a><span data-ttu-id="32e18-102">EditModeEnum</span><span class="sxs-lookup"><span data-stu-id="32e18-102">EditModeEnum</span></span>

<span data-ttu-id="32e18-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="32e18-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="32e18-104">指定记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="32e18-104">Specifies the editing status of a record.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="32e18-105">常量</span><span class="sxs-lookup"><span data-stu-id="32e18-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="32e18-106">值</span><span class="sxs-lookup"><span data-stu-id="32e18-106">Value</span></span></p></th>
<th><p><span data-ttu-id="32e18-107">说明</span><span class="sxs-lookup"><span data-stu-id="32e18-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32e18-108"><strong>为 adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="32e18-108"><strong>adEditNone</strong></span></span></p></td>
<td><p><span data-ttu-id="32e18-109">0</span><span class="sxs-lookup"><span data-stu-id="32e18-109">0</span></span></p></td>
<td><p><span data-ttu-id="32e18-110">指示没有正在进行的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="32e18-110">Indicates that no editing operation is in progress.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32e18-111"><strong>adEditInProgress</strong></span><span class="sxs-lookup"><span data-stu-id="32e18-111"><strong>adEditInProgress</strong></span></span></p></td>
<td><p><span data-ttu-id="32e18-112">1</span><span class="sxs-lookup"><span data-stu-id="32e18-112">1</span></span></p></td>
<td><p><span data-ttu-id="32e18-113">指示当前记录中的数据已经修改但未保存。</span><span class="sxs-lookup"><span data-stu-id="32e18-113">Indicates that data in the current record has been modified but not saved.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32e18-114"><strong>adEditAdd</strong></span><span class="sxs-lookup"><span data-stu-id="32e18-114"><strong>adEditAdd</strong></span></span></p></td>
<td><p><span data-ttu-id="32e18-115">2</span><span class="sxs-lookup"><span data-stu-id="32e18-115">2</span></span></p></td>
<td><p><span data-ttu-id="32e18-116">指示已调用 <a href="addnew-method-ado.md">AddNew</a> 方法，且复制缓冲区中的当前记录是尚未保存在数据库中保存的新记录。</span><span class="sxs-lookup"><span data-stu-id="32e18-116">Indicates that the <a href="addnew-method-ado.md">AddNew</a> method has been called, and the current record in the copy buffer is a new record that has not been saved in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32e18-117"><strong>adEditDelete</strong></span><span class="sxs-lookup"><span data-stu-id="32e18-117"><strong>adEditDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="32e18-118">4</span><span class="sxs-lookup"><span data-stu-id="32e18-118">4</span></span></p></td>
<td><p><span data-ttu-id="32e18-119">指示已删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="32e18-119">Indicates that the current record has been deleted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="32e18-120">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="32e18-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="32e18-121">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="32e18-121">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="32e18-122">常量</span><span class="sxs-lookup"><span data-stu-id="32e18-122">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32e18-123">AdoEnums.EditMode.NONE</span><span class="sxs-lookup"><span data-stu-id="32e18-123">AdoEnums.EditMode.NONE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32e18-124">AdoEnums.EditMode.INPROGRESS</span><span class="sxs-lookup"><span data-stu-id="32e18-124">AdoEnums.EditMode.INPROGRESS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32e18-125">AdoEnums.EditMode.ADD</span><span class="sxs-lookup"><span data-stu-id="32e18-125">AdoEnums.EditMode.ADD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32e18-126">AdoEnums.EditMode.DELETE</span><span class="sxs-lookup"><span data-stu-id="32e18-126">AdoEnums.EditMode.DELETE</span></span></p></td>
</tr>
</tbody>
</table>

