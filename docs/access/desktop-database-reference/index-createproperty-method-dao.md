---
title: CreateProperty 方法 (DAO)
TOCTitle: CreateProperty Method
ms:assetid: 712bccd2-c8a8-cc96-6f77-6d93d92320d9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195775(v=office.15)
ms:contentKeyID: 48545578
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1d7fcaa959c0fa5f8d42d9b00a920e987ca2f126
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291836"
---
# <a name="indexcreateproperty-method-dao"></a>CreateProperty 方法 (DAO)

**适用于**：Access 2013、Office 2013

创建一个新的用户定义的 **[Property](property-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。CreateProperty (***Name***、 ***Type***、 ***Value***、 ***DDL***)

*表达式*一个代表**Index**对象的变量。

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
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个对新的 <strong>Property</strong> 对象进行唯一命名的 <strong>String</strong>。 有关有效 <strong>Property</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个定义新的 <strong>Property</strong> 对象的数据类型的常量。 有关有效数据类型, 请参阅<strong><a href="field-type-property-dao.md">Type</a></strong>属性。</p></td>
</tr>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个包含初始属性值的 <strong>Variant</strong>。 有关详细信息, 请参阅<strong><a href="field-value-property-dao.md">Value</a></strong>属性。</p></td>
</tr>
<tr class="even">
<td><p><em>DDL</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>Boolean</strong> 子类型），用于指示 <strong>Property</strong> 是否为 DDL 对象。 默认值为 <strong>False</strong> 。 如果 DDL 为<strong>True</strong>, 则用户不能更改或删除此<strong>属性</strong>对象, 除非他们具有<strong>dbSecWriteDef</strong>权限。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

属性

## <a name="remarks"></a>注解

只能在某个对象的永久 [**Properties**](properties-collection-dao.md) 集合中创建用户定义的 **Property** 对象。

如果使用 **CreateProperty** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅 **Name**、 **Type** 和 **Value** 属性主题。

如果 name 引用了已经是集合成员的对象, 则当您使用**[Append](fields-append-method-dao.md)** 方法时, 将发生运行时错误。

若要从集合中删除用户定义的 **Property** 对象，请对 **[Properties](fields-delete-method-dao.md)** 集合使用 **Delete** 方法。 不能删除内置属性。

> [!NOTE]
> 如果省略了 DDL 参数, 它的默认值为 False (非 DDL)。 由于未公开相应的 DDL 属性, 因此必须删除并重新创建要从 DDL 更改为非 ddl 的**property**对象。


