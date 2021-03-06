---
title: Append 方法（ADOX 键）
TOCTitle: Append method (ADOX Keys)
ms:assetid: 14d6e8d7-5c9e-a422-47d6-ebfd9dd7a120
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248913(v=office.15)
ms:contentKeyID: 48543396
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c301f6809ab7f785497637b12e0b5d7a0bb7772d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297086"
---
# <a name="append-method-adox-keys"></a>Append 方法（ADOX 键）

**适用于**：Access 2013、Office 2013

将新的 [Key](key-object-adox.md) 对象添加到 [Keys](keys-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*键*。Append*Key* \[、*KeyType* \] \[、** \] Column \[、** RelatedTable\] ** 、RelatedColumn \[\]

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Key* |要追加的 **Key** 对象，或者要创建并追加的键的名称。|
|*关键字* |可选。 指定键类型的 **Long** 值。 *Key* 参数对应于 **Key** 对象的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) 属性。|
|*列* |可选。**String** 值，指定要进行索引的列的名称。*Columns* 参数对应于 [Column](column-object-adox.md) 对象的 [Name](name-property-adox.md) 属性值。|
|*RelatedTable* |可选。指定相关表的名称的 **String** 值。*RelatedTable* 参数对应于 [Table](table-object-adox.md) 对象的 **Name** 属性值。|
|*RelatedColumn* |可选。 **String** 值，指定外键的相关列的名称。RelatedColumn 参数对应于 **Column** 对象的 **Name** 属性值。|

## <a name="remarks"></a>注解

*Columns* 参数可接受列名或列名数组。

