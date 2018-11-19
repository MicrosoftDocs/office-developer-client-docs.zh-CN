---
title: Precision 属性 (ADOX)
TOCTitle: Precision property (ADOX)
ms:assetid: 5d8ca497-572a-52e0-18aa-f82deaea0813
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249330(v=office.15)
ms:contentKeyID: 48545117
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 973e5e3a6d9c61a0fdc6b259a8a7b846b62af6fd
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026104"
---
# <a name="precision-property-adox"></a>Precision 属性 (ADOX)


**适用于**： Access 2013、 Office 2013

指示列中的数据值的最大精度。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Long** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为数值类型时数据值的最大精度。对于所有其他数据类型将忽略 **Precision** 。

## <a name="remarks"></a>备注

默认值为零 (0)。

对于已追加到集合中的 [Column](column-object-adox.md) 对象，此属性为只读。

