---
title: Item 属性 (ADO)
TOCTitle: Item property (ADO)
ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15)
ms:contentKeyID: 48545767
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e4afbb31fb95aeea66d9cf93624b95c8796e2d25
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949360"
---
# <a name="item-property-ado"></a>Item 属性 (ADO)

**适用于**： Access 2013、 Office 2013

按名称或序号指示集合的特定成员。

## <a name="syntax"></a>语法

将*对象*设置 = *集合*。Item (Index)

## <a name="return-value"></a>返回值

返回对象引用。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Index* |一个 **Variant** 表达式，其值为集合中对象的名称或序号。|

## <a name="remarks"></a>备注

使用 **Item** 属性可返回集合中的特定对象。 如果**项目**找不到对象对应于*Index*参数集合中，将导致出错。 此外，有些集合不支持命名对象；对于这些集合，必须使用序号引用。

**Item** 属性是所有集合的默认属性；因此，以下语法格式可互换：

```vb
    collection.Item (Index)
    collection (Index)
```
