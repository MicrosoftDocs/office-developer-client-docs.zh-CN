---
title: DBEngine 方法 (DAO)
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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294195"
---
# <a name="dbenginesetoption-method-dao"></a><span data-ttu-id="2ca6c-102">DBEngine 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="2ca6c-102">DBEngine.SetOption method (DAO)</span></span>

<span data-ttu-id="2ca6c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2ca6c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2ca6c-104">暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-104">Temporarily overrides values for the Microsoft Access database engine keys in the Windows Registry (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="2ca6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="2ca6c-105">Syntax</span></span>

<span data-ttu-id="2ca6c-106">*表达式*。SetOption (***Option***, ***Value***)</span><span class="sxs-lookup"><span data-stu-id="2ca6c-106">*expression* .SetOption(***Option***, ***Value***)</span></span>

<span data-ttu-id="2ca6c-107">*表达式*一个返回**DBEngine**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-107">*expression* An expression that returns a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="2ca6c-108">参数</span><span class="sxs-lookup"><span data-stu-id="2ca6c-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2ca6c-109">名称</span><span class="sxs-lookup"><span data-stu-id="2ca6c-109">Name</span></span></p></th>
<th><p><span data-ttu-id="2ca6c-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="2ca6c-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="2ca6c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="2ca6c-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="2ca6c-112">说明</span><span class="sxs-lookup"><span data-stu-id="2ca6c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-113"><em>选项</em></span><span class="sxs-lookup"><span data-stu-id="2ca6c-113"><em>Option</em></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-114">必需</span><span class="sxs-lookup"><span data-stu-id="2ca6c-114">Required</span></span></p></td>
<td><p><span data-ttu-id="2ca6c-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-116">“说明”中描述的常量。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-116">A constant as described in Remarks.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-117"><em>Value</em></span><span class="sxs-lookup"><span data-stu-id="2ca6c-117"><em>Value</em></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-118">必需</span><span class="sxs-lookup"><span data-stu-id="2ca6c-118">Required</span></span></p></td>
<td><p><span data-ttu-id="2ca6c-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-120">要设置选项的值。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-120">The value that you want to set option to.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2ca6c-121">注解</span><span class="sxs-lookup"><span data-stu-id="2ca6c-121">Remarks</span></span>

<span data-ttu-id="2ca6c-122">每个常量\_都是指 path HKEY LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\引擎引擎\\ACE 中相应的注册表项 (即**dbSharedAsyncDelay**对应于注册表项 HKEY\_本地\_机器\\软件\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\引擎\\ACE\\SharedAsyncDelay 等)。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-122">Each constant refers to the corresponding registry key in the path HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE (that is, **dbSharedAsyncDelay** corresponds to the key HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\Engines\\ACE\\SharedAsyncDelay, and so on).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2ca6c-123">常量</span><span class="sxs-lookup"><span data-stu-id="2ca6c-123">Constant</span></span></p></th>
<th><p><span data-ttu-id="2ca6c-124">说明</span><span class="sxs-lookup"><span data-stu-id="2ca6c-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-125"><strong>dbPageTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-125"><strong>dbPageTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-126">PageTimeout 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-126">The PageTimeout key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-127"><strong>dbSharedAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-127"><strong>dbSharedAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-128">SharedAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-128">The SharedAsyncDelay key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-129"><strong>dbExclusiveAsyncDelay</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-129"><strong>dbExclusiveAsyncDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-130">ExclusiveAsyncDelay 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-130">The ExclusiveAsyncDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-131"><strong>dbLockRetry</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-131"><strong>dbLockRetry</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-132">LockRetry 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-132">The LockRetry key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-133"><strong>dbUserCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-133"><strong>dbUserCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-134">UserCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-134">The UserCommitSync key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-135"><strong>dbImplicitCommitSync</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-135"><strong>dbImplicitCommitSync</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-136">ImplicitCommitSync 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-136">The ImplicitCommitSync key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-137"><strong>dbMaxBufferSize</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-137"><strong>dbMaxBufferSize</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-138">MaxBufferSize 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-138">The MaxBufferSize key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-139"><strong>dbMaxLocksPerFile</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-139"><strong>dbMaxLocksPerFile</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-140">MaxLocksPerFile 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-140">The MaxLocksPerFile key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-141"><strong>dbLockDelay</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-141"><strong>dbLockDelay</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-142">LockDelay 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-142">The LockDelay key</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca6c-143"><strong>dbRecycleLVs</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-143"><strong>dbRecycleLVs</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-144">RecycleLVs 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-144">The RecycleLVs key</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca6c-145"><strong>dbFlushTransactionTimeout</strong></span><span class="sxs-lookup"><span data-stu-id="2ca6c-145"><strong>dbFlushTransactionTimeout</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca6c-146">FlushTransactionTimeout 项</span><span class="sxs-lookup"><span data-stu-id="2ca6c-146">The FlushTransactionTimeout key</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ca6c-p101">运行时使用 **SetOption** 方法替代注册表值。使用 **SetOption** 方法建立的新值在被另一个 **SetOption** 调用再次更改之前，或者在关闭 **DBEngine** 对象之前将保持有效。</span><span class="sxs-lookup"><span data-stu-id="2ca6c-p101">Use the **SetOption** method to override registry values at run-time. New values established with the **SetOption** method remain in effect until changed again by another **SetOption** call, or until the **DBEngine** object is closed.</span></span>

