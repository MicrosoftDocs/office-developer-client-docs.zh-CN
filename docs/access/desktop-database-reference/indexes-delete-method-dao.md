---
title: Indexes.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: 8d3c3221-3b2e-15ba-32ff-f2dfc592d82c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197351(v=office.15)
ms:contentKeyID: 48546252
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6ab52f353b7a3e636f64ff2ad6ad5354d62bed48
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703543"
---
# <a name="indexesdelete-method-dao"></a>Indexes.Delete 方法 (DAO)

**适用于**： Access 2013、 Office 2013

从 **Indexes** 集合中删除指定的 **Index**。

## <a name="syntax"></a>语法

*表达式*。删除 （***名称***）

*表达式*一个代表**Indexes**对象的变量。

## <a name="parameters"></a>Parameters

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>要删除的索引的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

仅当**Index**对象的新且未被追加到数据库时，才支持**Delete**方法。

