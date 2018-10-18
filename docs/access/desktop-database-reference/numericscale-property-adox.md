---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale Property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c8cc48c2f5b2b7cc58d21890435f0d959ad1e414
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605868"
---
# <a name="numericscale-property-adox"></a>NumericScale 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指示列中数值的小数位数。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置和返回一个 **Byte** 值，该值为当列的 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。

## <a name="remarks"></a>备注

默认值为零 (0)。

对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。

