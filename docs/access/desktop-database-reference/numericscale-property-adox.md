---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d706bad7d1f605933a951498705657c3c454a2d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288516"
---
# <a name="numericscale-property-adox"></a>NumericScale 属性 (ADOX)


**适用于**：Access 2013、Office 2013

指示列中数值的小数位数。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Byte** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。

## <a name="remarks"></a>注解

默认值为零 (0)。

对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。

