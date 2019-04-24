---
title: 轴集合 (ADO MD)
TOCTitle: Axes collection (ADO MD)
ms:assetid: 7c719197-45f1-a5b9-665d-25cb693b1eb0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249520(v=office.15)
ms:contentKeyID: 48545836
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8183b0bad1dcbaba33088dffcf21959f5b9fd993
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296932"
---
# <a name="axes-collection-ado-md"></a>轴集合 (ADO MD)


**适用于**：Access 2013、Office 2013

包含定义单元格集的 [Axis](axis-object-ado-md.md) 对象。

## <a name="remarks"></a>注解

[Cellset](cellset-object-ado-md.md) 对象包含 **Axes** 集合。一旦打开了 **Cellset** ，此集合将包含至少一个 **Axis** 。有关如何使用 [Axis](axis-object-ado-md.md) 对象的更详细说明，请参阅 **Axis** 对象。


> [!NOTE]
> [!注释] **Cellset** 的筛选轴不包含在 **Axes** 集合中。有关详细信息，请参阅 [FilterAxis](filteraxis-property-ado-md.md) 属性。



**Axes** 是一个标准 ADO 集合。使用集合的属性和方法，可以执行下列操作：

- 使用 [Count](count-property-ado.md) 属性获取集合中的对象数。

- 使用默认的 [Item](item-property-ado.md) 属性返回集合中的某个对象。

- 使用 [Refresh](refresh-method-ado.md) 方法更新来自提供程序的集合中的对象。

