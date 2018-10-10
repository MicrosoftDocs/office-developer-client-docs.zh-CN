---
title: ConnectModeEnum （访问桌面数据库参考 （英文）
TOCTitle: ConnectModeEnum
ms:assetid: a15aa733-f899-5fe9-e705-67a4301706d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249743(v=office.15)
ms:contentKeyID: 48546728
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5b39fc42259a1906891b82bf9b9ef252997e6240
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468423"
---
# <a name="connectmodeenum"></a><span data-ttu-id="388c1-102">ConnectModeEnum</span><span class="sxs-lookup"><span data-stu-id="388c1-102">ConnectModeEnum</span></span>


<span data-ttu-id="388c1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="388c1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="388c1-104">指定可用于执行以下操作的权限：修改 [Connection](connection-object-ado.md) 中的数据、打开 [Record](record-object-ado.md)，或指定 [Record](mode-property-ado.md) 和 **Stream** 对象的 [Mode](stream-object-ado.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="388c1-104">Specifies the available permissions for modifying data in a [Connection](connection-object-ado.md), opening a [Record](record-object-ado.md), or specifying values for the [Mode](mode-property-ado.md) property of the **Record** and [Stream](stream-object-ado.md) objects.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="388c1-105">常量</span><span class="sxs-lookup"><span data-stu-id="388c1-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="388c1-106">值</span><span class="sxs-lookup"><span data-stu-id="388c1-106">Value</span></span></p></th>
<th><p><span data-ttu-id="388c1-107">说明</span><span class="sxs-lookup"><span data-stu-id="388c1-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="388c1-108"><strong>adModeRead</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-108"><strong>adModeRead</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-109">1</span><span class="sxs-lookup"><span data-stu-id="388c1-109">1</span></span></p></td>
<td><p><span data-ttu-id="388c1-110">指示只读属性。</span><span class="sxs-lookup"><span data-stu-id="388c1-110">Indicates read-only permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-111"><strong>adModeReadWrite</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-111"><strong>adModeReadWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-112">3</span><span class="sxs-lookup"><span data-stu-id="388c1-112">3</span></span></p></td>
<td><p><span data-ttu-id="388c1-113">指示读/写权限。</span><span class="sxs-lookup"><span data-stu-id="388c1-113">Indicates read/write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-114"><strong>adModeRecursive</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-114"><strong>adModeRecursive</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-115">0x400000</span><span class="sxs-lookup"><span data-stu-id="388c1-115">0x400000</span></span></p></td>
<td><p><span data-ttu-id="388c1-116">与其他<em>*ShareDeny*</em>值 （<strong>adModeShareDenyNone</strong>、 <strong>adModeShareDenyWrite</strong>或<strong>adModeShareDenyRead</strong>） 传播到所有子记录当前<strong>记录</strong>的共享限制结合使用。</span><span class="sxs-lookup"><span data-stu-id="388c1-116">Used in conjunction with the other <em>*ShareDeny*</em> values (<strong>adModeShareDenyNone</strong>, <strong>adModeShareDenyWrite</strong>, or <strong>adModeShareDenyRead</strong>) to propagate sharing restrictions to all sub-records of the current <strong>Record</strong>.</span></span> <span data-ttu-id="388c1-117">如果<strong>记录</strong>不具有任何子级，它会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="388c1-117">It has no affect if the <strong>Record</strong> does not have any children.</span></span> <span data-ttu-id="388c1-118">如果与<strong>adModeShareDenyNone</strong>仅使用，则生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="388c1-118">A run-time error is generated if it is used with <strong>adModeShareDenyNone</strong> only.</span></span> <span data-ttu-id="388c1-119">但是，它可以与<strong>adModeShareDenyNone</strong>与其他值结合时使用。</span><span class="sxs-lookup"><span data-stu-id="388c1-119">However, it can be used with <strong>adModeShareDenyNone</strong> when combined with other values.</span></span> <span data-ttu-id="388c1-120">例如，您可以使用&quot; <strong>adModeRead</strong>或<strong>adModeShareDenyNone</strong>或<strong>adModeRecursive</strong>&quot;。</span><span class="sxs-lookup"><span data-stu-id="388c1-120">For example, you can use &quot;<strong>adModeRead</strong> Or <strong>adModeShareDenyNone</strong> Or <strong>adModeRecursive</strong>&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-121"><strong>adModeShareDenyNone</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-121"><strong>adModeShareDenyNone</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-122">16</span><span class="sxs-lookup"><span data-stu-id="388c1-122">16</span></span></p></td>
<td><p><span data-ttu-id="388c1-p102">允许他人以任何权限打开连接。不能拒绝他人的读访问或写访问。</span><span class="sxs-lookup"><span data-stu-id="388c1-p102">Allows others to open a connection with any permissions. Neither read nor write access can be denied to others.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-125"><strong>adModeShareDenyRead</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-125"><strong>adModeShareDenyRead</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-126">4</span><span class="sxs-lookup"><span data-stu-id="388c1-126">4</span></span></p></td>
<td><p><span data-ttu-id="388c1-127">禁止他人以读权限打开连接。</span><span class="sxs-lookup"><span data-stu-id="388c1-127">Prevents others from opening a connection with read permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-128"><strong>adModeShareDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-128"><strong>adModeShareDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-129">8</span><span class="sxs-lookup"><span data-stu-id="388c1-129">8</span></span></p></td>
<td><p><span data-ttu-id="388c1-130">禁止他人以写权限打开连接。</span><span class="sxs-lookup"><span data-stu-id="388c1-130">Prevents others from opening a connection with write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-131"><strong>adModeShareExclusive</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-131"><strong>adModeShareExclusive</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-132">12</span><span class="sxs-lookup"><span data-stu-id="388c1-132">12</span></span></p></td>
<td><p><span data-ttu-id="388c1-133">禁止其他人打开连接。</span><span class="sxs-lookup"><span data-stu-id="388c1-133">Prevents others from opening a connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-134"><strong>adModeUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-134"><strong>adModeUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-135">0</span><span class="sxs-lookup"><span data-stu-id="388c1-135">0</span></span></p></td>
<td><p><span data-ttu-id="388c1-p103">默认值。指示尚未设置权限或者无法确定权限。</span><span class="sxs-lookup"><span data-stu-id="388c1-p103">Default. Indicates that the permissions have not yet been set or cannot be determined.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-138"><strong>adModeWrite</strong></span><span class="sxs-lookup"><span data-stu-id="388c1-138"><strong>adModeWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="388c1-139">2</span><span class="sxs-lookup"><span data-stu-id="388c1-139">2</span></span></p></td>
<td><p><span data-ttu-id="388c1-140">指示只写权限。</span><span class="sxs-lookup"><span data-stu-id="388c1-140">Indicates write-only permissions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="388c1-141">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="388c1-141">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="388c1-142">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="388c1-142">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="388c1-143">常量</span><span class="sxs-lookup"><span data-stu-id="388c1-143">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="388c1-144">AdoEnums.ConnectMode.READ</span><span class="sxs-lookup"><span data-stu-id="388c1-144">AdoEnums.ConnectMode.READ</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-145">AdoEnums.ConnectMode.READWRITE</span><span class="sxs-lookup"><span data-stu-id="388c1-145">AdoEnums.ConnectMode.READWRITE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-146">（没有 AdoEnums.ConnectMode.RECURSIVE 的等效值）</span><span class="sxs-lookup"><span data-stu-id="388c1-146">(There is no equivalent of AdoEnums.ConnectMode.RECURSIVE)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-147">AdoEnums.ConnectMode.SHAREDENYNONE</span><span class="sxs-lookup"><span data-stu-id="388c1-147">AdoEnums.ConnectMode.SHAREDENYNONE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-148">AdoEnums.ConnectMode.SHAREDENYREAD</span><span class="sxs-lookup"><span data-stu-id="388c1-148">AdoEnums.ConnectMode.SHAREDENYREAD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-149">AdoEnums.ConnectMode.SHAREDENYWRITE</span><span class="sxs-lookup"><span data-stu-id="388c1-149">AdoEnums.ConnectMode.SHAREDENYWRITE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-150">AdoEnums.ConnectMode.SHAREEXCLUSIVE</span><span class="sxs-lookup"><span data-stu-id="388c1-150">AdoEnums.ConnectMode.SHAREEXCLUSIVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="388c1-151">AdoEnums.ConnectMode.UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="388c1-151">AdoEnums.ConnectMode.UNKNOWN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="388c1-152">AdoEnums.ConnectMode.WRITE</span><span class="sxs-lookup"><span data-stu-id="388c1-152">AdoEnums.ConnectMode.WRITE</span></span></p></td>
</tr>
</tbody>
</table>

