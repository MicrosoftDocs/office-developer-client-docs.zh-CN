---
title: Ordinal 属性 (ADO MD Position)
TOCTitle: Ordinal Property (ADO MD Position)
ms:assetid: fb132ab5-d2b5-317d-e885-5e37ddaf90fb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250284(v=office.15)
ms:contentKeyID: 48548861
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: efe0fcd48d3575651096b30853c3680b0284cf52
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876797"
---
# <a name="ordinal-property-ado-md-position"></a>Ordinal 属性 (ADO MD Position)


**适用于**： Access 2013、 Office 2013

唯一标识轴上的某个位置。

## <a name="return-values"></a>返回值

返回一个 **Long** 整数值，并且该值为只读。

## <a name="remarks"></a>备注

**Position** 对象的 [Ordinal](position-object-ado-md.md) 对应于 **Positions** 集合中该 [Position](positions-collection-ado-md.md) 的索引。

将 **Position** 在每根轴上的 **Ordinal** 与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性结合使用，可快速检索单元格。

