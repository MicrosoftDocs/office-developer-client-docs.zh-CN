---
title: Indexes.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: 8d3c3221-3b2e-15ba-32ff-f2dfc592d82c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197351(v=office.15)
ms:contentKeyID: 48546252
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0c725919b6509b5c802502fc8280823c407516f6
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998824"
---
# <a name="indexesdelete-method-dao"></a>Indexes.Delete 方法 (DAO)

**适用于**： Access 2013、 Office 2013

从 **Indexes** 集合中删除指定的 **Index**。

## <a name="syntax"></a>语法

*表达式*。删除 （***名称***）

*表达式*一个代表**Indexes**对象的变量。

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
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>要删除的索引的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

仅当**Index**对象的新且未被追加到数据库时，才支持**Delete**方法。

