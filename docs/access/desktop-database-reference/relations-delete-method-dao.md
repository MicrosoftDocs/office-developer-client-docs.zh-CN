---
title: Relations.Delete Method (DAO)
TOCTitle: Delete Method
ms:assetid: e95408d2-9dde-44e7-875e-8f2d4b837cf6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836064(v=office.15)
ms:contentKeyID: 48548438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1a7ad2345e547232b79085ec5942ce5ca7d8b5c8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870021"
---
# <a name="relationsdelete-method-dao"></a>Relations.Delete Method (DAO)


**适用于**： Access 2013、 Office 2013

从 **Relations** 集合中删除指定的 **Relation**。

## <a name="syntax"></a>语法

*表达式*。删除 （***名称***）

*表达式*一个代表**Relations**对象的变量。

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
<td><p>名称</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>要删除的关系的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

仅当 **Relation** 对象是新的未追加对象时，才支持 **Delete** 方法。

