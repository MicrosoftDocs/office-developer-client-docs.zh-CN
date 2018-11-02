---
title: DBEngine.SetOption 方法 (DAO)
TOCTitle: SetOption Method
ms:assetid: ea55c10c-2385-1b7e-0cba-32982c9b6643
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836236(v=office.15)
ms:contentKeyID: 48548461
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1088781
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 5e0282d95a77f302103414df1ee904d300a0330e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922949"
---
# <a name="dbenginesetoption-method-dao"></a><span data-ttu-id="d29eb-102">DBEngine.SetOption 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="d29eb-102">DBEngine.SetOption method (DAO)</span></span>


<span data-ttu-id="d29eb-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d29eb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d29eb-104">暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="d29eb-104">Temporarily overrides values for the Microsoft Access database engine keys in the Windows Registry (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="d29eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="d29eb-105">Syntax</span></span>

<span data-ttu-id="d29eb-106">*表达式*。SetOption （***选项***，***值***）</span><span class="sxs-lookup"><span data-stu-id="d29eb-106">*expression* .SetOption(***Option***, ***Value***)</span></span>

<span data-ttu-id="d29eb-107">*表达式*一个返回**DBEngine**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="d29eb-107">*expression* An expression that returns a **DBEngine** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="d29eb-108">参数</span><span class="sxs-lookup"><span data-stu-id="d29eb-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d29eb-109">名称</span><span class="sxs-lookup"><span data-stu-id="d29eb-109">Name</span></span></p></th>
<th><p><span data-ttu-id="d29eb-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="d29eb-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="d29eb-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="d29eb-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="d29eb-112">说明</span><span class="sxs-lookup"><span data-stu-id="d29eb-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-113">选项</span><span class="sxs-lookup"><span data-stu-id="d29eb-113">Option</span></span></p></td>
<td><p><span data-ttu-id="d29eb-114">必需</span><span class="sxs-lookup"><span data-stu-id="d29eb-114">Required</span></span></p></td>
<td><p><span data-ttu-id="d29eb-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-116">“说明”中描述的常量。</span><span class="sxs-lookup"><span data-stu-id="d29eb-116">A constant as described in Remarks.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-117">值</span><span class="sxs-lookup"><span data-stu-id="d29eb-117">Value</span></span></p></td>
<td><p><span data-ttu-id="d29eb-118">必需</span><span class="sxs-lookup"><span data-stu-id="d29eb-118">Required</span></span></p></td>
<td><p><span data-ttu-id="d29eb-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-120">您想要将选项设置为值。</span><span class="sxs-lookup"><span data-stu-id="d29eb-120">The value that you want to set option to.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d29eb-121">说明</span><span class="sxs-lookup"><span data-stu-id="d29eb-121">Remarks</span></span>

<span data-ttu-id="d29eb-122">每个常量引用路径 HKEY 中相应的注册表项\_本地\_计算机\\软件\\Microsoft\\Office\\12.0\\Access Connectivity 引擎\\引擎\\（即，ACE**dbSharedAsyncDelay**对应于键 HKEY\_本地\_计算机\\软件\\Microsoft\\Office\\12.0\\Access Connectivity 引擎\\引擎\\ACE\\SharedAsyncDelay，等等)。</span><span class="sxs-lookup"><span data-stu-id="d29eb-122">Each constant refers to the corresponding registry key in the path HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE (that is, **dbSharedAsyncDelay** corresponds to the key HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE\\SharedAsyncDelay, and so on).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d29eb-123">常量</span><span class="sxs-lookup"><span data-stu-id="d29eb-123">Constant</span></span></p></th>
<th><p><span data-ttu-id="d29eb-124">说明</span><span class="sxs-lookup"><span data-stu-id="d29eb-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-125"><strong>dbPageTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-125"><strong>dbPageTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-126">PageTimeout 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-126">The PageTimeout key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-127"><strong>dbSharedAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-127"><strong>dbSharedAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-128">SharedAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-128">The SharedAsyncDelay key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-129"><strong>dbExclusiveAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-129"><strong>dbExclusiveAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-130">ExclusiveAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-130">The ExclusiveAsyncDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-131"><strong>dbLockRetry</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-131"><strong>dbLockRetry</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-132">LockRetry 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-132">The LockRetry key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-133"><strong>dbUserCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-133"><strong>dbUserCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-134">UserCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-134">The UserCommitSync key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-135"><strong>dbImplicitCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-135"><strong>dbImplicitCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-136">ImplicitCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-136">The ImplicitCommitSync key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-137"><strong>dbMaxBufferSize</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-137"><strong>dbMaxBufferSize</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-138">MaxBufferSize 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-138">The MaxBufferSize key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-139"><strong>dbMaxLocksPerFile</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-139"><strong>dbMaxLocksPerFile</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-140">MaxLocksPerFile 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-140">The MaxLocksPerFile key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-141"><strong>dbLockDelay</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-141"><strong>dbLockDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-142">LockDelay 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-142">The LockDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29eb-143"><strong>dbRecycleLVs</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-143"><strong>dbRecycleLVs</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-144">RecycleLVs 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-144">The RecycleLVs key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d29eb-145"><strong>dbFlushTransactionTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="d29eb-145"><strong>dbFlushTransactionTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="d29eb-146">FlushTransactionTimeout 项</span><span class="sxs-lookup"><span data-stu-id="d29eb-146">The FlushTransactionTimeout key</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d29eb-p101">运行时使用 **SetOption** 方法替代注册表值。使用 **SetOption** 方法建立的新值在被另一个 **SetOption** 调用再次更改之前，或者在关闭 **DBEngine** 对象之前将保持有效。</span><span class="sxs-lookup"><span data-stu-id="d29eb-p101">Use the **SetOption** method to override registry values at run-time. New values established with the **SetOption** method remain in effect until changed again by another **SetOption** call, or until the **DBEngine** object is closed.</span></span>

