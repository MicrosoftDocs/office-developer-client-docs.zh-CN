---
title: Precision 属性 (ADO)
TOCTitle: Precision property (ADO)
ms:assetid: c9d54d78-d5a5-caf8-d635-259d1fcc0595
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249983(v=office.15)
ms:contentKeyID: 48547685
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 662e5e9287da1ccfb81c727f5d5e5dfedce2969b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287473"
---
# <a name="precision-property-ado"></a>Precision 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示 [Parameter](parameter-object-ado.md) 对象或数字 [Field](field-object-ado.md) 对象中数值的精度。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Byte** 值，指示用于表示值的最大位数。

## <a name="remarks"></a>注解

使用 **Precision** 属性可确定用于表示数字型 **Parameter** 或 **Field** 对象的值的最大位数。

在 **Parameter** 对象上该值为可读/写。

对于 **Field** 对象， **Precision** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **Precision** 才为可读/写。

