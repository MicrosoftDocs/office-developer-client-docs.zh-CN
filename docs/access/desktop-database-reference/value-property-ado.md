---
title: Value 属性 (ADO)
TOCTitle: Value property (ADO)
ms:assetid: ff21d122-98e3-2b48-d92f-e696b8079fc5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250310(v=office.15)
ms:contentKeyID: 48548958
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 00b82706d934356621ac1e41fffca61ec88e081f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715065"
---
# <a name="value-property-ado"></a>Value 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示赋给 [Field](field-object-ado.md)、[Parameter](parameter-object-ado.md) 或 [Property](property-object-ado.md) 对象的值。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个指示对象的值的 **Variant** 值。默认值取决于 [Type](type-property-ado.md) 属性。

## <a name="remarks"></a>备注

使用 **Value** 属性可以设置或返回来自 **Field** 对象的数据，设置或返回 **Parameter** 对象的参数值，或者设置或返回 **Property** 对象的属性设置。 **Value** 属性为可读/写还是只读属性取决于许多因素，有关详细信息，请参阅各个对象主题。

ADO 允许设置和返回 **Value** 属性的长二进制数据。

> [!NOTE]
> [!注释] 对于 **Parameter** 对象，ADO 只从提供程序那里读取一次 **Value** 属性。如果某命令包含 **Value** 属性为空的 **Parameter** 并且将使用该命令来创建 [Recordset](recordset-object-ado.md)，则请确保首先关闭 **Recordset** ，然后再检索 **Value** 属性。否则，对于某些提供程序， **Value** 属性可能为空，并且不包含正确的值。

对于已追加到 **Record** 对象的 [Fields](fields-collection-ado.md) 集合中的新 [Field](record-object-ado.md) 对象，必须先设置 **Value** 属性，然后才能指定其他任何 **Field** 属性。首先，必须为 **Value** 属性赋予特定值，并对 [Fields](update-method-ado.md) 集合调用 **Update**。然后，可以访问诸如 [Type](type-property-ado.md) 或 [Attributes](attributes-property-ado.md) 等其他属性。

