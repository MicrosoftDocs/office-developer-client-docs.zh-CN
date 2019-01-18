---
title: Ordinal 属性（ADO MD 单元格）
TOCTitle: Ordinal property (ADO MD Cell)
ms:assetid: be705823-6c5e-0c8f-f780-87df19423a72
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249924(v=office.15)
ms:contentKeyID: 48547462
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 91b8d66929e360f88385b6773a03fcaffb79161d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717410"
---
# <a name="ordinal-property-ado-md-cell"></a>Ordinal 属性（ADO MD 单元格）


**适用于**： Access 2013、 Office 2013

根据单元格在单元格集内的位置唯一标识该单元格。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，并且该值为只读。

## <a name="remarks"></a>备注

单元格的序号值唯一地标识单元格集中的单元格。从概念上来说，单元格在单元格集中进行了编号，就像单元格集是一个 *p* 维数组那样（此处 *p* 是 [Axes 集合 (ADO MD)](axes-collection-ado-md.md) 数目）。单元格按以行为主的顺序从零开始编号。

将单元格的序号值与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性一起使用，可以快速检索 [Cell 对象 (ADO MD)](cell-object-ado-md.md)。

