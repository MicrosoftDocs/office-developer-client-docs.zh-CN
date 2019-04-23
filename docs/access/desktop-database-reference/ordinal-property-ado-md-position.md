---
title: Ordinal 属性（ADO MD 位置）
TOCTitle: Ordinal property (ADO MD Position)
ms:assetid: fb132ab5-d2b5-317d-e885-5e37ddaf90fb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250284(v=office.15)
ms:contentKeyID: 48548861
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2e29b5c86e8f37d84116aa92432e93eb8943e29e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288188"
---
# <a name="ordinal-property-ado-md-position"></a>Ordinal 属性（ADO MD 位置）


**适用于**：Access 2013、Office 2013

唯一标识轴上的某个位置。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，并且该值为只读。

## <a name="remarks"></a>注解

[Position](position-object-ado-md.md) 对象的 **Ordinal** 对应于 [Positions](positions-collection-ado-md.md) 集合中该 **Position** 的索引。

将 **Position** 在每根轴上的 **Ordinal** 与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性结合使用，可快速检索单元格。

