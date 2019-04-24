---
title: Description 属性 (ADO)
TOCTitle: Description property (ADO)
ms:assetid: 31df5e36-641c-d213-31fc-6244e2983327
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249092(v=office.15)
ms:contentKeyID: 48544064
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ba6d05aa1bfb626520af60a30279983bae6fa566
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293929"
---
# <a name="description-property-ado"></a>Description 属性 (ADO)


**适用于**：Access 2013、Office 2013

描述 [Error](error-object-ado.md) 对象。

## <a name="return-value"></a>返回值

返回一个包含错误说明的 **String** 值。

## <a name="remarks"></a>注解

使用 **Description** 属性可以获得错误的简短说明。对于无法处理或不希望处理的错误，可以显示此属性来向用户发出警告。该字符串将来自 ADO 或提供程序。

提供程序负责向 ADO 传递具体的错误文本。对于收到的每个提供程序错误或警告，ADO 都会向 [Errors](error-object-ado.md) 集合添加一个 **Error** 对象。通过枚举 **Errors** 集合，可以跟踪提供程序所传递的错误。

