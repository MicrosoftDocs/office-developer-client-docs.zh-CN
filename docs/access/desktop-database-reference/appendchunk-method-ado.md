---
title: AppendChunk 方法 (ADO)
TOCTitle: AppendChunk method (ADO)
ms:assetid: 3fa931a3-2cd7-a3b0-a750-40e18bc9937e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249179(v=office.15)
ms:contentKeyID: 48544405
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 89a75ebe8a3fe704c4f755a0f744eac4d068ec0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297023"
---
# <a name="appendchunk-method-ado"></a>AppendChunk 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将数据追加到大型文本或二进制数据 [Field](field-object-ado.md) 或 [Parameter](parameter-object-ado.md) 对象。

## <a name="syntax"></a>语法

*对象。* AppendChunk*数据*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*object* |**Field** 或 **Parameter** 对象。|
|*Data* |**变量型** ，包含要追加到对象的数据。|

## <a name="remarks"></a>注解

可以对 **Field** 或 **Parameter** 对象使用 **AppendChunk** 方法，用长型二进制或字符数据来填充该对象。如果系统内存有限，那么在处理长型数值时可以用 **AppendChunk** 方法将整个数据分成若干部分。

### <a name="field"></a>Field

如果 **Field** 对象的 [Attributes](attributes-property-ado.md) 属性中的 **adFldLong** 位设置为 True，那么可以对该字段使用 **AppendChunk** 方法。

对 **Field** 对象第一次调用 **AppendChunk** 时，将数据写入字段，覆盖所有现有数据。之后调用 **AppendChunk** 时，在现有数据基础上进行添加。如果将数据追加到某个字段，然后设置或读取当前记录中另一个字段的值，那么 ADO 会假设您已完成了对第一个字段的数据追加。此时如果对第一个字段再次调用 **AppendChunk** 方法，则 ADO 会将调用解释为新的 **AppendChunk** 操作并覆盖现有数据。访问并非第一个 [Recordset](recordset-object-ado.md) 对象克隆的其他 **Recordset** 对象中的字段时，不会中断 **AppendChunk** 操作。

如果在对 **Field** 对象调用 **AppendChunk** 时当前没有记录，则会发生错误。

> [!NOTE]
> [!注释] **AppendChunk** 方法不能对 **Record** 对象的 [Field](record-object-ado.md) 对象进行操作。它不执行任何操作，并将产生运行时错误。

### <a name="parameters"></a>参数

如果 **Parameter** 对象的 **Attributes** 属性中的 **adParamLong** 位设置为 True，那么可以对该参数使用 **AppendChunk** 方法。

对 **Parameter** 对象第一次调用 **AppendChunk** 时，将数据写入参数，覆盖所有现有数据。之后对 **Parameter** 对象调用 **AppendChunk** 时，在现有参数数据基础上进行添加。如果 **AppendChunk** 调用传递的是 Null 值，则将放弃所有参数数据。

