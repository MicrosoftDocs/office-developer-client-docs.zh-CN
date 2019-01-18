---
title: DefinedSize 属性 (ADO)
TOCTitle: DefinedSize property (ADO)
ms:assetid: 8d6db4c9-fbdc-9fcd-63f0-bd677c5ebcf6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249619(v=office.15)
ms:contentKeyID: 48546257
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 121e81734fc5ecc0a761dae53942f1cbed98df2a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715324"
---
# <a name="definedsize-property-ado"></a>DefinedSize 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示 [Field](field-object-ado.md) 对象的数据容量。

## <a name="return-value"></a>返回值

返回一个 **Long** 值，该值以字节数反映字段的定义大小。

## <a name="remarks"></a>备注

使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。

**DefinedSize** 和 [ActualSize](actualsize-property-ado.md) 属性不同。例如，假如声明类型为 **adVarChar** 且 **DefinedSize** 属性值为 50 的 **Field** 对象中只包含了一个字符。其返回的 **ActualSize** 属性值为单个字符所占的字节长度。

