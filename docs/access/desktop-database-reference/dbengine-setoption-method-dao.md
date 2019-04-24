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
# <a name="dbenginesetoption-method-dao"></a>DBEngine 方法 (DAO)

**适用于**：Access 2013、Office 2013

暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。SetOption (***Option***, ***Value***)

*表达式*一个返回**DBEngine**对象的表达式。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>选项</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>“说明”中描述的常量。</p></td>
</tr>
<tr class="even">
<td><p><em>Value</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>要设置选项的值。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

每个常量\_都是指 path HKEY LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\引擎引擎\\ACE 中相应的注册表项 (即**dbSharedAsyncDelay**对应于注册表项 HKEY\_本地\_机器\\软件\\Microsoft\\Office\\12.0\\Access Connectivity Engine\\引擎\\ACE\\SharedAsyncDelay 等)。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbPageTimeout</strong></p></td>
<td><p>PageTimeout 项</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSharedAsyncDelay</strong></p></td>
<td><p>SharedAsyncDelay 项</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbExclusiveAsyncDelay</strong></p></td>
<td><p>ExclusiveAsyncDelay 项</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLockRetry</strong></p></td>
<td><p>LockRetry 项</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbUserCommitSync</strong></p></td>
<td><p>UserCommitSync 项</p></td>
</tr>
<tr class="even">
<td><p><strong>dbImplicitCommitSync</strong></p></td>
<td><p>ImplicitCommitSync 项</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbMaxBufferSize</strong></p></td>
<td><p>MaxBufferSize 项</p></td>
</tr>
<tr class="even">
<td><p><strong>dbMaxLocksPerFile</strong></p></td>
<td><p>MaxLocksPerFile 项</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLockDelay</strong></p></td>
<td><p>LockDelay 项</p></td>
</tr>
<tr class="even">
<td><p><strong>dbRecycleLVs</strong></p></td>
<td><p>RecycleLVs 项</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbFlushTransactionTimeout</strong></p></td>
<td><p>FlushTransactionTimeout 项</p></td>
</tr>
</tbody>
</table>


运行时使用 **SetOption** 方法替代注册表值。使用 **SetOption** 方法建立的新值在被另一个 **SetOption** 调用再次更改之前，或者在关闭 **DBEngine** 对象之前将保持有效。

