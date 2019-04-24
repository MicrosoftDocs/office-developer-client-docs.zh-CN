---
title: ConnectModeEnum (Access desktop database reference)
TOCTitle: ConnectModeEnum
ms:assetid: a15aa733-f899-5fe9-e705-67a4301706d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249743(v=office.15)
ms:contentKeyID: 48546728
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 453d84e687a31f7df5082e17b80fe2a1bda756be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295693"
---
# <a name="connectmodeenum"></a><span data-ttu-id="222de-102">ConnectModeEnum</span><span class="sxs-lookup"><span data-stu-id="222de-102">ConnectModeEnum</span></span>

<span data-ttu-id="222de-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="222de-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="222de-104">指定可用于执行以下操作的权限：修改 [Connection](connection-object-ado.md) 中的数据、打开 [Record](record-object-ado.md)，或指定 **Record** 和 [Stream](stream-object-ado.md) 对象的 [Mode](mode-property-ado.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="222de-104">Specifies the available permissions for modifying data in a [Connection](connection-object-ado.md), opening a [Record](record-object-ado.md), or specifying values for the [Mode](mode-property-ado.md) property of the **Record** and [Stream](stream-object-ado.md) objects.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="222de-105">常量</span><span class="sxs-lookup"><span data-stu-id="222de-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="222de-106">值</span><span class="sxs-lookup"><span data-stu-id="222de-106">Value</span></span></p></th>
<th><p><span data-ttu-id="222de-107">说明</span><span class="sxs-lookup"><span data-stu-id="222de-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222de-108"><strong>adModeRead</strong></span><span class="sxs-lookup"><span data-stu-id="222de-108"><strong>adModeRead</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-109">1</span><span class="sxs-lookup"><span data-stu-id="222de-109">1</span></span></p></td>
<td><p><span data-ttu-id="222de-110">指示只读属性。</span><span class="sxs-lookup"><span data-stu-id="222de-110">Indicates read-only permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-111"><strong>adModeReadWrite</strong></span><span class="sxs-lookup"><span data-stu-id="222de-111"><strong>adModeReadWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-112">第三章</span><span class="sxs-lookup"><span data-stu-id="222de-112">3</span></span></p></td>
<td><p><span data-ttu-id="222de-113">指示读/写权限。</span><span class="sxs-lookup"><span data-stu-id="222de-113">Indicates read/write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-114"><strong>adModeRecursive</strong></span><span class="sxs-lookup"><span data-stu-id="222de-114"><strong>adModeRecursive</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-115">0x400000</span><span class="sxs-lookup"><span data-stu-id="222de-115">0x400000</span></span></p></td>
<td><p><span data-ttu-id="222de-116">与其他<em>*ShareDeny*</em>值 (<strong>adModeShareDenyNone</strong>、 <strong>adModeShareDenyWrite</strong>或<strong>adModeShareDenyRead</strong>) 结合使用, 以将共享限制传播到当前<strong>记录</strong>的所有子记录。</span><span class="sxs-lookup"><span data-stu-id="222de-116">Used in conjunction with the other <em>*ShareDeny*</em> values (<strong>adModeShareDenyNone</strong>, <strong>adModeShareDenyWrite</strong>, or <strong>adModeShareDenyRead</strong>) to propagate sharing restrictions to all sub-records of the current <strong>Record</strong>.</span></span> <span data-ttu-id="222de-117">如果 <strong>Record</strong> 没有任何子记录，则该值无效。</span><span class="sxs-lookup"><span data-stu-id="222de-117">It has no affect if the <strong>Record</strong> does not have any children.</span></span></p><p><span data-ttu-id="222de-118">如果将它仅与 <strong>adModeShareDenyNone</strong> 一起使用，将生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="222de-118">A run-time error is generated if it is used with <strong>adModeShareDenyNone</strong> only.</span></span> <span data-ttu-id="222de-119">但是，当与其他值组合使用时，可以将它与 <strong>adModeShareDenyNone</strong> 一起使用。</span><span class="sxs-lookup"><span data-stu-id="222de-119">However, it can be used with <strong>adModeShareDenyNone</strong> when combined with other values.</span></span> <span data-ttu-id="222de-120">例如, 可以使用&quot; <strong>adModeRead</strong>或<strong>adModeShareDenyNone</strong>或<strong>adModeRecursive</strong>&quot;。</span><span class="sxs-lookup"><span data-stu-id="222de-120">For example, you can use &quot;<strong>adModeRead</strong> or <strong>adModeShareDenyNone</strong> or <strong>adModeRecursive</strong>&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-121"><strong>adModeShareDenyNone</strong></span><span class="sxs-lookup"><span data-stu-id="222de-121"><strong>adModeShareDenyNone</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-122">位</span><span class="sxs-lookup"><span data-stu-id="222de-122">16</span></span></p></td>
<td><p><span data-ttu-id="222de-p103">允许他人以任何权限打开连接。不能拒绝他人的读访问或写访问。</span><span class="sxs-lookup"><span data-stu-id="222de-p103">Allows others to open a connection with any permissions. Neither read nor write access can be denied to others.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-125"><strong>adModeShareDenyRead</strong></span><span class="sxs-lookup"><span data-stu-id="222de-125"><strong>adModeShareDenyRead</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-126">4</span><span class="sxs-lookup"><span data-stu-id="222de-126">4</span></span></p></td>
<td><p><span data-ttu-id="222de-127">禁止他人以读权限打开连接。</span><span class="sxs-lookup"><span data-stu-id="222de-127">Prevents others from opening a connection with read permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-128"><strong>adModeShareDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="222de-128"><strong>adModeShareDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-129">utf-8</span><span class="sxs-lookup"><span data-stu-id="222de-129">8</span></span></p></td>
<td><p><span data-ttu-id="222de-130">禁止他人以写权限打开连接。</span><span class="sxs-lookup"><span data-stu-id="222de-130">Prevents others from opening a connection with write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-131"><strong>adModeShareExclusive</strong></span><span class="sxs-lookup"><span data-stu-id="222de-131"><strong>adModeShareExclusive</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-132">12</span><span class="sxs-lookup"><span data-stu-id="222de-132">12</span></span></p></td>
<td><p><span data-ttu-id="222de-133">禁止其他人打开连接。</span><span class="sxs-lookup"><span data-stu-id="222de-133">Prevents others from opening a connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-134"><strong>adModeUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="222de-134"><strong>adModeUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-135">0</span><span class="sxs-lookup"><span data-stu-id="222de-135">0</span></span></p></td>
<td><p><span data-ttu-id="222de-p104">默认值。指示尚未设置权限或者无法确定权限。</span><span class="sxs-lookup"><span data-stu-id="222de-p104">Default. Indicates that the permissions have not yet been set or cannot be determined.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-138"><strong>adModeWrite</strong></span><span class="sxs-lookup"><span data-stu-id="222de-138"><strong>adModeWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="222de-139">双面</span><span class="sxs-lookup"><span data-stu-id="222de-139">2</span></span></p></td>
<td><p><span data-ttu-id="222de-140">指示只写权限。</span><span class="sxs-lookup"><span data-stu-id="222de-140">Indicates write-only permissions.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="222de-141">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="222de-141">ADO/WFC equivalent</span></span>

<span data-ttu-id="222de-142">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="222de-142">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="222de-143">常量</span><span class="sxs-lookup"><span data-stu-id="222de-143">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222de-144">AdoEnums。请参阅 ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-144">AdoEnums.ConnectMode.READ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-145">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-145">AdoEnums.ConnectMode.READWRITE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-146">（没有 AdoEnums.ConnectMode.RECURSIVE 的等效值）</span><span class="sxs-lookup"><span data-stu-id="222de-146">(There is no equivalent of AdoEnums.ConnectMode.RECURSIVE)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-147">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-147">AdoEnums.ConnectMode.SHAREDENYNONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-148">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-148">AdoEnums.ConnectMode.SHAREDENYREAD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-149">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-149">AdoEnums.ConnectMode.SHAREDENYWRITE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-150">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-150">AdoEnums.ConnectMode.SHAREEXCLUSIVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222de-151">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-151">AdoEnums.ConnectMode.UNKNOWN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222de-152">AdoEnums ConnectMode</span><span class="sxs-lookup"><span data-stu-id="222de-152">AdoEnums.ConnectMode.WRITE</span></span></p></td>
</tr>
</tbody>
</table>

