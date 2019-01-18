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
localization_priority: Normal
ms.openlocfilehash: 5875a8935b1b44c3c36b29344af32df552f6e01c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699889"
---
# <a name="dbenginesetoption-method-dao"></a><span data-ttu-id="ddb12-102">DBEngine.SetOption 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ddb12-102">DBEngine.SetOption method (DAO)</span></span>

<span data-ttu-id="ddb12-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ddb12-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ddb12-104">暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ddb12-104">Temporarily overrides values for the Microsoft Access database engine keys in the Windows Registry (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="ddb12-105">语法</span><span class="sxs-lookup"><span data-stu-id="ddb12-105">Syntax</span></span>

<span data-ttu-id="ddb12-106">*表达式*。SetOption （***选项***，***值***）</span><span class="sxs-lookup"><span data-stu-id="ddb12-106">*expression* .SetOption(***Option***, ***Value***)</span></span>

<span data-ttu-id="ddb12-107">*表达式*一个返回**DBEngine**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="ddb12-107">*expression* An expression that returns a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="ddb12-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="ddb12-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ddb12-109">Name</span><span class="sxs-lookup"><span data-stu-id="ddb12-109">Name</span></span></p></th>
<th><p><span data-ttu-id="ddb12-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="ddb12-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="ddb12-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="ddb12-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="ddb12-112">说明</span><span class="sxs-lookup"><span data-stu-id="ddb12-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-113"><em>选项</em></span><span class="sxs-lookup"><span data-stu-id="ddb12-113"><em>Option</em></span></span></p></td>
<td><p><span data-ttu-id="ddb12-114">必需</span><span class="sxs-lookup"><span data-stu-id="ddb12-114">Required</span></span></p></td>
<td><p><span data-ttu-id="ddb12-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-116">“说明”中描述的常量。</span><span class="sxs-lookup"><span data-stu-id="ddb12-116">A constant as described in Remarks.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-117"><em>Value</em></span><span class="sxs-lookup"><span data-stu-id="ddb12-117"><em>Value</em></span></span></p></td>
<td><p><span data-ttu-id="ddb12-118">必需</span><span class="sxs-lookup"><span data-stu-id="ddb12-118">Required</span></span></p></td>
<td><p><span data-ttu-id="ddb12-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-120">您想要将选项设置为值。</span><span class="sxs-lookup"><span data-stu-id="ddb12-120">The value that you want to set option to.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ddb12-121">备注</span><span class="sxs-lookup"><span data-stu-id="ddb12-121">Remarks</span></span>

<span data-ttu-id="ddb12-122">每个常量引用路径 HKEY 中相应的注册表项\_本地\_计算机\\软件\\Microsoft\\Office\\12.0\\Access Connectivity 引擎\\引擎\\（即，ACE**dbSharedAsyncDelay**对应于键 HKEY\_本地\_计算机\\软件\\Microsoft\\Office\\12.0\\Access Connectivity 引擎\\引擎\\ACE\\SharedAsyncDelay，等等)。</span><span class="sxs-lookup"><span data-stu-id="ddb12-122">Each constant refers to the corresponding registry key in the path HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE (that is, **dbSharedAsyncDelay** corresponds to the key HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE\\SharedAsyncDelay, and so on).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ddb12-123">常量</span><span class="sxs-lookup"><span data-stu-id="ddb12-123">Constant</span></span></p></th>
<th><p><span data-ttu-id="ddb12-124">说明</span><span class="sxs-lookup"><span data-stu-id="ddb12-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-125"><strong>dbPageTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-125"><strong>dbPageTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-126">PageTimeout 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-126">The PageTimeout key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-127"><strong>dbSharedAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-127"><strong>dbSharedAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-128">SharedAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-128">The SharedAsyncDelay key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-129"><strong>dbExclusiveAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-129"><strong>dbExclusiveAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-130">ExclusiveAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-130">The ExclusiveAsyncDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-131"><strong>dbLockRetry</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-131"><strong>dbLockRetry</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-132">LockRetry 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-132">The LockRetry key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-133"><strong>dbUserCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-133"><strong>dbUserCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-134">UserCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-134">The UserCommitSync key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-135"><strong>dbImplicitCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-135"><strong>dbImplicitCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-136">ImplicitCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-136">The ImplicitCommitSync key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-137"><strong>dbMaxBufferSize</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-137"><strong>dbMaxBufferSize</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-138">MaxBufferSize 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-138">The MaxBufferSize key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-139"><strong>dbMaxLocksPerFile</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-139"><strong>dbMaxLocksPerFile</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-140">MaxLocksPerFile 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-140">The MaxLocksPerFile key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-141"><strong>dbLockDelay</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-141"><strong>dbLockDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-142">LockDelay 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-142">The LockDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb12-143"><strong>dbRecycleLVs</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-143"><strong>dbRecycleLVs</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-144">RecycleLVs 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-144">The RecycleLVs key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb12-145"><strong>dbFlushTransactionTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="ddb12-145"><strong>dbFlushTransactionTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="ddb12-146">FlushTransactionTimeout 项</span><span class="sxs-lookup"><span data-stu-id="ddb12-146">The FlushTransactionTimeout key</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ddb12-p101">运行时使用 **SetOption** 方法替代注册表值。使用 **SetOption** 方法建立的新值在被另一个 **SetOption** 调用再次更改之前，或者在关闭 **DBEngine** 对象之前将保持有效。</span><span class="sxs-lookup"><span data-stu-id="ddb12-p101">Use the **SetOption** method to override registry values at run-time. New values established with the **SetOption** method remain in effect until changed again by another **SetOption** call, or until the **DBEngine** object is closed.</span></span>

