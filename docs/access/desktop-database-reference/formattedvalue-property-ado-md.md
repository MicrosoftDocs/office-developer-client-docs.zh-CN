---
title: FormattedValue 属性 (ADO MD)
TOCTitle: FormattedValue property (ADO MD)
ms:assetid: ea7962f2-b08b-52c9-34e5-c5490c72662f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250189(v=office.15)
ms:contentKeyID: 48548464
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d750944cd42feb95b09f53382c54329ea0c32e1d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292312"
---
# <a name="formattedvalue-property-ado-md"></a>FormattedValue 属性 (ADO MD)


**适用于**：Access 2013、Office 2013

指示单元格值的格式化显示。

## <a name="return-values"></a>返回值

返回一个 **String** 值，并且该值为只读。

## <a name="remarks"></a>注解

使用 **FormattedValue** 属性可获取 [Cell](cell-object-ado-md.md) 对象的 [Value](value-property-ado-md.md) 属性的带格式显示值。例如，如果单元格值为 1056.87，并且此值表示一个美元金额，则 **FormattedValue** 为 $1,056.87。

