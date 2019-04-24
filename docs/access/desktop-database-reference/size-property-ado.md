---
title: Size 属性 (ADO)
TOCTitle: Size property (ADO)
ms:assetid: 24596b5c-b1cc-e97e-68b6-8ff53baf150b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249017(v=office.15)
ms:contentKeyID: 48543753
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2a1bed3454d081b9d5de3a01e9b326130b40baa4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306928"
---
# <a name="size-property-ado"></a>Size 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示 [Parameter](parameter-object-ado.md) 对象的最大大小，以字节或字符为单位。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个指示 **Parameter** 对象最大大小的 **Long** 值，以字节或字符为单位。

## <a name="remarks"></a>注解

使用 **Size** 属性可确定写入 **Parameter** 对象的 [Value](value-property-ado.md) 属性或从中读取的值的最大大小。

如果要指定 **Parameter** 对象为可变长度数据类型（例如，任何 **String** 类型，如 **adVarChar**），则必须先设置对象的 **Size** 属性，然后再将该对象追加到 [Parameters](parameters-collection-ado.md) 集合；否则，将发生错误。

如果已经将 **Parameter** 对象追加到 [Command](command-object-ado.md) 对象的  **Parameters** 集合，并已经将它的类型更改为可变长度数据类型，那么必须先设置 **Parameter** 对象的 **Size** 属性，然后再执行 **Command** 对象；否则，将发生错误。

如果使用 [Refresh](refresh-method-ado.md) 方法从提供程序获取参数信息，并且提供程序返回一个或多个可变长度数据类型的 **Parameter** 对象，则 ADO 可能会根据其最大可能大小为其分配内存空间，这样在执行过程中可能会导致错误。为避免出错，应该在执行命令之前显式设置这些参数的 **Size** 属性。

**Size** 为可读/写属性。

