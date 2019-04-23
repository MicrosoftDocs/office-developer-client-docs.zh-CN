---
title: Precision 属性 (ADOX)
TOCTitle: Precision property (ADOX)
ms:assetid: 5d8ca497-572a-52e0-18aa-f82deaea0813
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249330(v=office.15)
ms:contentKeyID: 48545117
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f05f6880a9599421189519f263cfb27bf1432325
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287480"
---
# <a name="precision-property-adox"></a>Precision 属性 (ADOX)


**适用于**：Access 2013、Office 2013

指示列中的数据值的最大精度。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Long** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为数值类型时数据值的最大精度。对于所有其他数据类型将忽略 **Precision** 。

## <a name="remarks"></a>注解

默认值为零 (0)。

对于已追加到集合中的 [Column](column-object-adox.md) 对象，此属性为只读。

