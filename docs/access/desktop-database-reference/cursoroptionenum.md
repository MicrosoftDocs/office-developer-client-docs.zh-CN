---
title: 个 CursorOptionEnum （访问桌面数据库参考 （英文）
TOCTitle: CursorOptionEnum
ms:assetid: 3c118c08-02f2-5290-1cef-29e97c35fddc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249155(v=office.15)
ms:contentKeyID: 48544303
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 9dda0ef3b268c164e1bb1f8fbad91f96328c30c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881984"
---
# <a name="cursoroptionenum"></a><span data-ttu-id="0db6e-102">CursorOptionEnum</span><span class="sxs-lookup"><span data-stu-id="0db6e-102">CursorOptionEnum</span></span>

<span data-ttu-id="0db6e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0db6e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0db6e-104">指定应针对哪项功能来测试 [Supports](supports-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="0db6e-104">Specifies what functionality the [Supports](supports-method-ado.md) method should test for.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0db6e-105">常量</span><span class="sxs-lookup"><span data-stu-id="0db6e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="0db6e-106">值</span><span class="sxs-lookup"><span data-stu-id="0db6e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="0db6e-107">说明</span><span class="sxs-lookup"><span data-stu-id="0db6e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-108"><strong>adAddNew</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-108"><strong>adAddNew</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-109">0x1000400</span><span class="sxs-lookup"><span data-stu-id="0db6e-109">0x1000400</span></span></p></td>
<td><p><span data-ttu-id="0db6e-110">支持 <a href="addnew-method-ado.md">AddNew</a> 方法以添加新记录。</span><span class="sxs-lookup"><span data-stu-id="0db6e-110">Supports the <a href="addnew-method-ado.md">AddNew</a> method to add new records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-111"><strong>adApproxPosition</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-111"><strong>adApproxPosition</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-112">0x4000</span><span class="sxs-lookup"><span data-stu-id="0db6e-112">0x4000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-113">支持 <a href="absoluteposition-property-ado.md">AbsolutePosition</a> 和 <a href="absolutepage-property-ado.md">AbsolutePage</a> 属性。</span><span class="sxs-lookup"><span data-stu-id="0db6e-113">Supports the <a href="absoluteposition-property-ado.md">AbsolutePosition</a> and <a href="absolutepage-property-ado.md">AbsolutePage</a> properties.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-114"><strong>adBookmark</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-114"><strong>adBookmark</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-115">0x2000</span><span class="sxs-lookup"><span data-stu-id="0db6e-115">0x2000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-116">支持 <a href="bookmark-property-ado.md">Bookmark</a> 属性以获取对特定记录的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0db6e-116">Supports the <a href="bookmark-property-ado.md">Bookmark</a> property to gain access to specific records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-117"><strong>adDelete</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-117"><strong>adDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-118">0x1000800</span><span class="sxs-lookup"><span data-stu-id="0db6e-118">0x1000800</span></span></p></td>
<td><p><span data-ttu-id="0db6e-119">支持 <a href="delete-method-ado-recordset.md">Delete</a> 方法以删除记录。</span><span class="sxs-lookup"><span data-stu-id="0db6e-119">Supports the <a href="delete-method-ado-recordset.md">Delete</a> method to delete records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-120"><strong>adFind</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-120"><strong>adFind</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-121">0x80000</span><span class="sxs-lookup"><span data-stu-id="0db6e-121">0x80000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-122">支持 <a href="find-method-ado.md">Find</a> 方法以便在 <a href="recordset-object-ado.md">Recordset</a> 中查找行。</span><span class="sxs-lookup"><span data-stu-id="0db6e-122">Supports the <a href="find-method-ado.md">Find</a> method to locate a row in a <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-123"><strong>adHoldRecords</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-123"><strong>adHoldRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-124">0x100</span><span class="sxs-lookup"><span data-stu-id="0db6e-124">0x100</span></span></p></td>
<td><p><span data-ttu-id="0db6e-125">检索多个记录或更改下一个位置（不提交所有挂起更改）。</span><span class="sxs-lookup"><span data-stu-id="0db6e-125">Retrieves more records or changes the next position without committing all pending changes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-126"><strong>adIndex</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-126"><strong>adIndex</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-127">0x100000</span><span class="sxs-lookup"><span data-stu-id="0db6e-127">0x100000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-128">支持 <a href="index-property-ado.md">Index</a> 属性以命名索引。</span><span class="sxs-lookup"><span data-stu-id="0db6e-128">Supports the <a href="index-property-ado.md">Index</a> property to name an index.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-129"><strong>adMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-129"><strong>adMovePrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-130">0x200</span><span class="sxs-lookup"><span data-stu-id="0db6e-130">0x200</span></span></p></td>
<td><p><span data-ttu-id="0db6e-131">支持 <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a> 和 <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a> 方法，以及 <a href="move-method-ado.md">Move</a> 或 <a href="getrows-method-ado.md">GetRows</a> 方法，以便向后移动当前记录位置而不需要书签。</span><span class="sxs-lookup"><span data-stu-id="0db6e-131">Supports the <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a> and <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a> methods, and <a href="move-method-ado.md">Move</a> or <a href="getrows-method-ado.md">GetRows</a> methods to move the current record position backward without requiring bookmarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-132"><strong>adNotify</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-132"><strong>adNotify</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-133">而 0x40000 可</span><span class="sxs-lookup"><span data-stu-id="0db6e-133">0x40000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-134">指示基础数据提供程序支持通知（用于确定是否支持 <strong>Recordset</strong> 事件）。</span><span class="sxs-lookup"><span data-stu-id="0db6e-134">Indicates that the underlying data provider supports notifications (which determines whether <strong>Recordset</strong> events are supported).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-135"><strong>adResync</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-135"><strong>adResync</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-136">0x20000</span><span class="sxs-lookup"><span data-stu-id="0db6e-136">0x20000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-137">支持 <a href="resync-method-ado.md">Resync</a> 方法，以使用在基础数据库中可见的数据来更新游标。</span><span class="sxs-lookup"><span data-stu-id="0db6e-137">Supports the <a href="resync-method-ado.md">Resync</a> method to update the cursor with the data that is visible in the underlying database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-138"><strong>adSeek</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-138"><strong>adSeek</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-139">0x200000</span><span class="sxs-lookup"><span data-stu-id="0db6e-139">0x200000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-140">支持 <a href="seek-method-ado.md">Seek</a> 方法，以便在 <strong>Recordset</strong> 中查找行。</span><span class="sxs-lookup"><span data-stu-id="0db6e-140">Supports the <a href="seek-method-ado.md">Seek</a> method to locate a row in a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-141"><strong>adUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-141"><strong>adUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-142">0x1008000</span><span class="sxs-lookup"><span data-stu-id="0db6e-142">0x1008000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-143">支持 <a href="update-method-ado.md">Update</a> 方法以修改现有数据。</span><span class="sxs-lookup"><span data-stu-id="0db6e-143">Supports the <a href="update-method-ado.md">Update</a> method to modify existing data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-144"><strong>adUpdateBatch</strong></span><span class="sxs-lookup"><span data-stu-id="0db6e-144"><strong>adUpdateBatch</strong></span></span></p></td>
<td><p><span data-ttu-id="0db6e-145">0x10000</span><span class="sxs-lookup"><span data-stu-id="0db6e-145">0x10000</span></span></p></td>
<td><p><span data-ttu-id="0db6e-146">支持批更新（<a href="updatebatch-method-ado.md">UpdateBatch</a> 和 <a href="cancelbatch-method-ado.md">CancelBatch</a> 方法），以便将成组更改传输到提供程序。</span><span class="sxs-lookup"><span data-stu-id="0db6e-146">Supports batch updating (<a href="updatebatch-method-ado.md">UpdateBatch</a> and <a href="cancelbatch-method-ado.md">CancelBatch</a> methods) to transmit groups of changes to the provider.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="0db6e-147">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="0db6e-147">ADO/WFC equivalent</span></span>

<span data-ttu-id="0db6e-148">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="0db6e-148">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0db6e-149">常量</span><span class="sxs-lookup"><span data-stu-id="0db6e-149">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-150">AdoEnums.CursorOption.ADDNEW</span><span class="sxs-lookup"><span data-stu-id="0db6e-150">AdoEnums.CursorOption.ADDNEW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-151">AdoEnums.CursorOption.APPROXPOSITION</span><span class="sxs-lookup"><span data-stu-id="0db6e-151">AdoEnums.CursorOption.APPROXPOSITION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-152">AdoEnums.CursorOption.BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="0db6e-152">AdoEnums.CursorOption.BOOKMARK</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-153">AdoEnums.CursorOption.DELETE</span><span class="sxs-lookup"><span data-stu-id="0db6e-153">AdoEnums.CursorOption.DELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-154">AdoEnums.CursorOption.FIND</span><span class="sxs-lookup"><span data-stu-id="0db6e-154">AdoEnums.CursorOption.FIND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-155">AdoEnums.CursorOption.HOLDRECORDS</span><span class="sxs-lookup"><span data-stu-id="0db6e-155">AdoEnums.CursorOption.HOLDRECORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-156">AdoEnums.CursorOption.INDEX</span><span class="sxs-lookup"><span data-stu-id="0db6e-156">AdoEnums.CursorOption.INDEX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-157">AdoEnums.CursorOption.MOVEPREVIOUS</span><span class="sxs-lookup"><span data-stu-id="0db6e-157">AdoEnums.CursorOption.MOVEPREVIOUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-158">AdoEnums.CursorOption.NOTIFY</span><span class="sxs-lookup"><span data-stu-id="0db6e-158">AdoEnums.CursorOption.NOTIFY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-159">AdoEnums.CursorOption.RESYNC</span><span class="sxs-lookup"><span data-stu-id="0db6e-159">AdoEnums.CursorOption.RESYNC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-160">AdoEnums.CursorOption.SEEK</span><span class="sxs-lookup"><span data-stu-id="0db6e-160">AdoEnums.CursorOption.SEEK</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db6e-161">AdoEnums.CursorOption.UPDATE</span><span class="sxs-lookup"><span data-stu-id="0db6e-161">AdoEnums.CursorOption.UPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db6e-162">AdoEnums.CursorOption.UPDATEBATCH</span><span class="sxs-lookup"><span data-stu-id="0db6e-162">AdoEnums.CursorOption.UPDATEBATCH</span></span></p></td>
</tr>
</tbody>
</table>

