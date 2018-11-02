---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c7dd53830216c302d68adf44e1bea88bbc52e980
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921311"
---
# <a name="numericscale-property-adox"></a>NumericScale 属性 (ADOX)


**适用于**： Access 2013、 Office 2013

指示列中数值的小数位数。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Byte** 值，该值为当列的 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。

## <a name="remarks"></a>备注

默认值为零 (0)。

对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。

