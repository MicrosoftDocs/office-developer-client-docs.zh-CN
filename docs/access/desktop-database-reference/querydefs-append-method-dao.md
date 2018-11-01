---
title: QueryDefs.Append Method (DAO)
TOCTitle: Append Method
ms:assetid: 9b62a26b-3b7c-6d26-7707-177b00a23178
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198041(v=office.15)
ms:contentKeyID: 48546570
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c152d52d2a89beaa82061d0d5ae1a5d8d25c1809
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888683"
---
# <a name="querydefsappend-method-dao"></a>QueryDefs.Append Method (DAO)


**适用于**： Access 2013、 Office 2013

将新的 **QueryDef** 添加到 **QueryDefs** 集合。

## <a name="syntax"></a>语法

*表达式*。追加 （***对象***）

*表达式*一个代表**QueryDefs**对象的变量。

### <a name="parameters"></a>参数

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
<td><p>对象</p></td>
<td><p>必需</p></td>
<td><p><strong>对象</strong></p></td>
<td><p>一个对象变量，代表追加到集合的字段。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。

添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。

如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。 例如，如果没有指定字段类型，然后尝试**将 Field**对象追加到**Fields**集合中的**TableDef**对象使用**Append**方法触发一个运行时错误。

