---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale Property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4229a318c4eb855b86164f02f1075d29a915d718
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467770"
---
# <a name="numericscale-property-adox"></a>NumericScale 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指示列中数值的小数位数。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Byte** 值，该值为当列的 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。

## <a name="remarks"></a>备注

默认值为零 (0)。

对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。

