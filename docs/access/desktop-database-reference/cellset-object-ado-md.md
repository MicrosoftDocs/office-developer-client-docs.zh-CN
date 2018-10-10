---
title: Cellset 对象 (ADO MD)
TOCTitle: Cellset Object (ADO MD)
ms:assetid: 28d4b3b9-f907-9ec0-00e1-9666c887cdf0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249047(v=office.15)
ms:contentKeyID: 48543869
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4f34d467d482386886539070a9cf137dd311bce2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468727"
---
# <a name="cellset-object-ado-md"></a>Cellset 对象 (ADO MD)

**适用于**： Access 2013 |Office 2013

代表多维查询的结果。它是从多维数据集或其他单元格集中选择的单元格的集合。

## <a name="remarks"></a>说明

**Cellset** 中的数据是使用直接、类似数组的访问方式检索的。您可以"向下钻取"到特定成员以获取有关该成员的信息。例如，以下代码返回名为 cst 的单元格集的第一个轴上第一个位置中第一个成员的标题：

`cst.Axes(0).Positions(0).Members(0).Caption`

单元格集中没有当前单元格的观念。[Item](item-property-ado-md-cellset.md) 属性而是从单元格集中检索特定 [Cell](cell-object-ado-md.md) 对象。 **Item** 属性的参数确定要检索的单元格。您可以指定单元格的唯一序号值。还可以使用单元格沿单元格集的每条轴的位置号来检索单元格。有关检索单元格的详细信息，请参阅 [Item](item-property-ado-md-cellset.md) 属性。

使用 **Cellset** 对象的集合和属性，可以执行下列操作：

  - 通过设置 **Cellset** 对象的 [ActiveConnection](activeconnection-property-ado-md.md) 属性，将打开的连接与该对象关联在一起。

  - 使用 [Open](open-method-ado-md.md) 方法执行和检索多维查询的结果。

  - 使用 **Item** 属性从 **Cellset** 中检索 [Cell](item-property-ado-md-cellset.md) 。

  - 使用 [Axes](axis-object-ado-md.md) 集合返回用于定义 **Cellset** 的 [Axis](axes-collection-ado-md.md) 对象。

  - 使用 **FilterAxis** 属性检索有关用于筛选 [Cellset](filteraxis-property-ado-md.md) 中的数据的维的信息。

  - 使用 **Source** 属性返回或指定用于定义 [Cellset](source-property-ado-md.md) 的查询。

  - 使用 **State** 属性返回 [Cellset](state-property-ado-md.md) 的当前状态（打开、关闭、正在执行或正在连接）。

  - 使用 **Close** 方法关闭打开的 [Cellset](close-method-ado-md.md) 。

  - 使用标准 ADO **Properties** 集合检索有关 [Cellset](properties-collection-ado.md) 的提供程序特定信息。

