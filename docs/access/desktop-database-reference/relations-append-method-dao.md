---
title: 关系. Append 方法 (DAO)
TOCTitle: Append Method
ms:assetid: dafcc7b8-b30d-2ba2-631d-eca0f882fc2d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835334(v=office.15)
ms:contentKeyID: 48548094
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052904
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: b8374832ad6cd6bac30fa9d129e54fb6ab4c8fd4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306984"
---
# <a name="relationsappend-method-dao"></a>关系. Append 方法 (DAO)

**适用于**：Access 2013、Office 2013

将新的 **Relation** 添加到 **Relations** 集合。

## <a name="syntax"></a>语法

*表达式*。Append (***Object***)

*表达式*一个代表**关系**对象的变量。

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
<td><p><em>Object</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Object</strong></p></td>
<td><p>一个对象变量，代表追加到集合的字段。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。

添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。

如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。 例如, 如果尚未指定字段类型, 然后尝试将**field**对象追加到**TableDef**对象中的**Fields**集合中, 则使用**append**方法将触发运行时错误。

