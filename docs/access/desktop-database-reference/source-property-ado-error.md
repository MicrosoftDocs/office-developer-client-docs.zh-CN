---
title: Source 属性（ADO 错误）
TOCTitle: Source property (ADO Error)
ms:assetid: ffc6c77f-1494-d63a-d832-416faa4c6f07
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250316(v=office.15)
ms:contentKeyID: 48548969
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f03dcc8049113df13ff8654aee340d1e2d6e502
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308594"
---
# <a name="source-property-ado-error"></a>Source 属性（ADO 错误）


**适用于**：Access 2013、Office 2013

指示最初生成错误的对象或应用程序的名称。

## <a name="return-value"></a>返回值

返回一个 **String** 值，指示对象或应用程序的名称。

## <a name="remarks"></a>注解

使用 [Error](error-object-ado.md) 对象上的 **Source** 属性可以确定生成错误的原始对象或应用程序的名称。 这可以是对象的类名或编程 ID。 对于 ADO 中的错误, 属性值将为 **ADODB。 * * * objectname*, 其中*ObjectName*是触发错误的对象的名称。 对于 ADOX 和 ADO MD, 值将分别为 **ADOX. * * *-objectname*和 **ADOMD. * * * objectname* 。

可以根据 **Error** 对象的 **Source**、[Number](number-property-ado.md) 和 [Description](description-property-ado.md) 属性的错误文档编写代码，以恰当地处理错误。

对于 **Error** 对象，**Source** 属性为只读属性。

