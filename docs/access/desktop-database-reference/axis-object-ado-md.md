---
title: Axis 对象 (ADO MD)
TOCTitle: Axis object (ADO MD)
ms:assetid: a4332b69-8900-08f1-a4e2-9395d005ed42
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249763(v=office.15)
ms:contentKeyID: 48546807
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e90ff31c0b6a78a3f242927e2fa7e84c42d6ab3
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945346"
---
# <a name="axis-object-ado-md"></a>Axis 对象 (ADO MD)


**适用于**： Access 2013、 Office 2013

代表单元格集的位置轴或筛选轴，包含一维或多维的选定成员。

## <a name="remarks"></a>说明

**Axis** 对象可以由 [Axes](axes-collection-ado-md.md) 集合包含，或者由 [Cellset](filteraxis-property-ado-md.md) 的 [FilterAxis](cellset-object-ado-md.md) 属性返回。

使用 **Axis** 对象的集合和属性，可以执行下列操作：

- 使用 **Name** 属性标识 [Axis](name-property-ado-md.md) 。

- 使用 **Positions** 集合遍历沿 [Axis](positions-collection-ado-md.md) 的每个位置。

- 使用 **DimensionCount** 属性获取 [Axis](dimensioncount-property-ado-md.md) 的维数。

- 使用标准 ADO **Properties** 集合获取 [Axis](properties-collection-ado.md) 的提供程序特定属性。

