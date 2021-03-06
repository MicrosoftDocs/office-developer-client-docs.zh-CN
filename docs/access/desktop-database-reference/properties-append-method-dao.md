---
title: Properties. Append 方法 (DAO)
TOCTitle: Append Method
ms:assetid: 47f1e24f-975c-3fdc-5c3c-8c91f2920c81
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193232(v=office.15)
ms:contentKeyID: 48544609
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 528809495ebefd15a8895b15a9d51f84e6892980
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301307"
---
# <a name="propertiesappend-method-dao"></a>Properties. Append 方法 (DAO)

**适用于**：Access 2013、Office 2013

将新的 **Property** 添加到 **Properties** 集合。

## <a name="syntax"></a>语法

*表达式*。Append (***Object***)

*表达式*一个代表**Properties**对象的变量。

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

