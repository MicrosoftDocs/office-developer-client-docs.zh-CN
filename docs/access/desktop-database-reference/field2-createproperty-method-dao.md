---
title: Field2.CreateProperty 方法 (DAO)
TOCTitle: CreateProperty Method
ms:assetid: bdbd6bec-216f-138e-78df-9c3221692aa4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822737(v=office.15)
ms:contentKeyID: 48547446
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1a101e736e72c0e00bd0b5efede91ae74e4f9754
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936684"
---
# <a name="field2createproperty-method-dao"></a>Field2.CreateProperty 方法 (DAO)


**适用于**： Access 2013、 Office 2013

创建一个新的用户定义的 **[Property](property-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。CreateProperty （***名称***、***类型***、***值***、 ***DDL***）

*表达式*一个代表**Field2**对象的变量。

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
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个对新的 <strong>Property</strong> 对象进行唯一命名的 <strong>String</strong>。有关有效 <strong>Property</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p>类型</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个定义新的 <strong>Property</strong> 对象的数据类型的常量。有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</p></td>
</tr>
<tr class="odd">
<td><p>值</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个包含初始属性值的 <strong>Variant</strong>。有关详细信息，请参阅 <strong><a href="field-value-property-dao.md">Value</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p>DDL</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong>Variant</strong> （<strong>布尔</strong>子类型），该值指示<strong>属性</strong>DDL 对象。 默认值为 <strong>False</strong> 。 如果 DDL 为<strong>True</strong>，则用户无法更改或删除此<strong>Property</strong>对象，除非他们具有<strong>dbSecWriteDef</strong>权限。</p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a>返回值

属性

## <a name="remarks"></a>注解

只能在某个对象的永久 [**Properties**](properties-collection-dao.md) 集合中创建用户定义的 **Property** 对象。

如果使用 **CreateProperty** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅 **Name**、 **Type** 和 **Value** 属性主题。

如果 name 引用对象的已经是集合的成员，使用**[Append](fields-append-method-dao.md)** 方法时，发生此事件运行时错误。

若要从集合中删除用户定义的 **Property** 对象，请对 **[Properties](fields-delete-method-dao.md)** 集合使用 **[Delete](properties-collection-dao.md)** 方法。不能删除内置属性。


> [!NOTE]
> 如果省略 DDL 参数，则默认为 False (非 DDL)。 由于没有公开相应的 DDL 属性，必须删除要从 DDL 更改为非 DDL 的 **Property** 对象，然后重新创建该对象。


