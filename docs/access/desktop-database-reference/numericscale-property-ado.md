---
title: NumericScale 属性 (ADO)
TOCTitle: NumericScale property (ADO)
ms:assetid: 51b232d2-5bfd-521c-f4e9-65655ecc7c70
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249263(v=office.15)
ms:contentKeyID: 48544824
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1bcb0c1a38108fbd02551df2a3296abe4d9a3791
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288551"
---
# <a name="numericscale-property-ado"></a>NumericScale 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示 [Parameter](parameter-object-ado.md) 或 [Field](field-object-ado.md) 对象中数值的小数位数。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Byte** 值，指示数值的小数位数。

## <a name="remarks"></a>注解

使用 **NumericScale** 属性可确定将用于表示数字型 **Parameter** 或 **Field** 对象的小数点后的数字个数。

对于 **Parameter** 对象， **NumericScale** 属性为可读/写属性。

对于 **Field** 对象， **NumericScale** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序已通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **NumericScale** 才为可读/写。

