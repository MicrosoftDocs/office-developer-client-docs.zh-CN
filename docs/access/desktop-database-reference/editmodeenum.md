---
title: EditModeEnum （访问桌面数据库参考 （英文）
TOCTitle: EditModeEnum
ms:assetid: 4da0e504-aca2-b769-04a2-0df687fa4422
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249248(v=office.15)
ms:contentKeyID: 48544737
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 790d28fa1efec5d5ad212094cb75f9d8d6456dbe
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860271"
---
# <a name="editmodeenum"></a><span data-ttu-id="509dd-102">EditModeEnum</span><span class="sxs-lookup"><span data-stu-id="509dd-102">EditModeEnum</span></span>

<span data-ttu-id="509dd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="509dd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="509dd-104">指定记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="509dd-104">Specifies the editing status of a record.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="509dd-105">常量</span><span class="sxs-lookup"><span data-stu-id="509dd-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="509dd-106">值</span><span class="sxs-lookup"><span data-stu-id="509dd-106">Value</span></span></p></th>
<th><p><span data-ttu-id="509dd-107">说明</span><span class="sxs-lookup"><span data-stu-id="509dd-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="509dd-108"><strong>为 adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="509dd-108"><strong>adEditNone</strong></span></span></p></td>
<td><p><span data-ttu-id="509dd-109">0</span><span class="sxs-lookup"><span data-stu-id="509dd-109">0</span></span></p></td>
<td><p><span data-ttu-id="509dd-110">指示没有正在进行的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="509dd-110">Indicates that no editing operation is in progress.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="509dd-111"><strong>adEditInProgress</strong></span><span class="sxs-lookup"><span data-stu-id="509dd-111"><strong>adEditInProgress</strong></span></span></p></td>
<td><p><span data-ttu-id="509dd-112">1</span><span class="sxs-lookup"><span data-stu-id="509dd-112">1</span></span></p></td>
<td><p><span data-ttu-id="509dd-113">指示当前记录中的数据已经修改但未保存。</span><span class="sxs-lookup"><span data-stu-id="509dd-113">Indicates that data in the current record has been modified but not saved.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="509dd-114"><strong>adEditAdd</strong></span><span class="sxs-lookup"><span data-stu-id="509dd-114"><strong>adEditAdd</strong></span></span></p></td>
<td><p><span data-ttu-id="509dd-115">2</span><span class="sxs-lookup"><span data-stu-id="509dd-115">2</span></span></p></td>
<td><p><span data-ttu-id="509dd-116">指示已调用 <a href="addnew-method-ado.md">AddNew</a> 方法，且复制缓冲区中的当前记录是尚未保存在数据库中保存的新记录。</span><span class="sxs-lookup"><span data-stu-id="509dd-116">Indicates that the <a href="addnew-method-ado.md">AddNew</a> method has been called, and the current record in the copy buffer is a new record that has not been saved in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="509dd-117"><strong>adEditDelete</strong></span><span class="sxs-lookup"><span data-stu-id="509dd-117"><strong>adEditDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="509dd-118">4</span><span class="sxs-lookup"><span data-stu-id="509dd-118">4</span></span></p></td>
<td><p><span data-ttu-id="509dd-119">指示已删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="509dd-119">Indicates that the current record has been deleted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="509dd-120">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="509dd-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="509dd-121">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="509dd-121">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="509dd-122">常量</span><span class="sxs-lookup"><span data-stu-id="509dd-122">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="509dd-123">AdoEnums.EditMode.NONE</span><span class="sxs-lookup"><span data-stu-id="509dd-123">AdoEnums.EditMode.NONE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="509dd-124">AdoEnums.EditMode.INPROGRESS</span><span class="sxs-lookup"><span data-stu-id="509dd-124">AdoEnums.EditMode.INPROGRESS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="509dd-125">AdoEnums.EditMode.ADD</span><span class="sxs-lookup"><span data-stu-id="509dd-125">AdoEnums.EditMode.ADD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="509dd-126">AdoEnums.EditMode.DELETE</span><span class="sxs-lookup"><span data-stu-id="509dd-126">AdoEnums.EditMode.DELETE</span></span></p></td>
</tr>
</tbody>
</table>

