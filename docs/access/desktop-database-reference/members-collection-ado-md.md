---
title: Members 集合 (ADO MD)
TOCTitle: Members collection (ADO MD)
ms:assetid: 1389c554-e4f1-107d-22c6-7fe851d53d23
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248910(v=office.15)
ms:contentKeyID: 48543371
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: adc8ed771bcba6a4b6532b33b27980f8aab695c5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721323"
---
# <a name="members-collection-ado-md"></a>Members 集合 (ADO MD)


**适用于**： Access 2013、 Office 2013

包含来自某个级别或轴上某个位置的 [Member](member-object-ado-md.md) 对象。

## <a name="remarks"></a>说明

**Members** 集合用于包含下列类型的成员：

  - 构成多维数据集中的某一级别的成员。它们包含在 **Level** 对象的 [Members](level-object-ado-md.md) 集合中。例如，使用 [多维架构和数据概述](overview-of-multidimensional-schemas-and-data.md)中的示例时，Countries 级别的四个成员为 Canada、USA、UK 和 Germany。

  - 属于层次结构中特定成员的子级的成员。这些成员由父 [Member](children-property-ado-md.md) 对象的 **Children** 属性返回。例如，还是使用同一示例，Canada 成员的两个子级为 Canada-East 和 Canada-West。

  - 定义沿[单元格集](cellset-object-ado-md.md)的轴的特定位置的成员。使用[处理多维数据](working-with-multidimensional-data.md)中的单元格集作为示例时，x 轴上第一个位置的两个成员为 Valentine 和 Seattle。这些成员包含在 **Position** 对象的 [Members](position-object-ado-md.md) 集合中。

**Members** 是一个标准 ADO 集合。使用集合的属性和方法，可以执行下列操作：

  - 使用 [Count](count-property-ado.md) 属性获取集合中的对象数。

  - 使用默认的 [Item](item-property-ado.md) 属性返回集合中的某个对象。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新来自提供程序的集合中的对象。

