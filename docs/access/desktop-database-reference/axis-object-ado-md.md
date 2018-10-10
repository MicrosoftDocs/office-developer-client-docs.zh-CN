---
title: Axis 对象 (ADO MD)
TOCTitle: Axis Object (ADO MD)
ms:assetid: a4332b69-8900-08f1-a4e2-9395d005ed42
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249763(v=office.15)
ms:contentKeyID: 48546807
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f978c5e6304e33ac67dfd4a669fe9155afb0b64d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466382"
---
# <a name="axis-object-ado-md"></a>Axis 对象 (ADO MD)


**适用于**： Access 2013 |Office 2013

代表单元格集的位置轴或筛选轴，包含一维或多维的选定成员。

## <a name="remarks"></a>说明

**Axis** 对象可以由 [Axes](axes-collection-ado-md.md) 集合包含，或者由 [Cellset](filteraxis-property-ado-md.md) 的 [FilterAxis](cellset-object-ado-md.md) 属性返回。

使用 **Axis** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 属性标识 [Axis](name-property-ado-md.md) 。

  - 使用 **Positions** 集合遍历沿 [Axis](positions-collection-ado-md.md) 的每个位置。

  - 使用 **DimensionCount** 属性获取 [Axis](dimensioncount-property-ado-md.md) 的维数。

  - 使用标准 ADO **Properties** 集合获取 [Axis](properties-collection-ado.md) 的提供程序特定属性。

