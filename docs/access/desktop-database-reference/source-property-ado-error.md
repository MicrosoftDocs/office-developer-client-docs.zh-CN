---
title: Source 属性（ADO 错误）
TOCTitle: Source property (ADO Error)
ms:assetid: ffc6c77f-1494-d63a-d832-416faa4c6f07
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250316(v=office.15)
ms:contentKeyID: 48548969
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 47ae7ea790265edc10be8c907869eefbe4e593ba
ms.sourcegitcommit: 66e74e39f44dca8c41f97f05528b8f9eb1aaed87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061305"
---
# <a name="source-property-ado-error"></a>Source 属性（ADO 错误）


**适用于**：Access 2013、Office 2013

指示最初生成错误的对象或应用程序的名称。

## <a name="return-value"></a>返回值

返回一个 **String** 值，指示对象或应用程序的名称。

## <a name="remarks"></a>备注

使用 [Error](error-object-ado.md) 对象上的 **Source** 属性可以确定生成错误的原始对象或应用程序的名称。 这可以是对象的类名或编程 ID。 对于 ADO 中的错误，该属性值将为 **ADODB.** *ObjectName*，其中 *ObjectName* 是触发错误的对象的名称。 对于 ADOX 和 ADO MD，该值将分别为 **ADOX.** *ObjectName* 和 **ADOMD.** *ObjectName*。

可以根据 **Error** 对象的 **Source**、[Number](number-property-ado.md) 和 [Description](description-property-ado.md) 属性的错误文档编写代码，以恰当地处理错误。

对于 **Error** 对象，**Source** 属性为只读属性。

