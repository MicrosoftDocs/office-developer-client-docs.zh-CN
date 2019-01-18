---
title: CreateParameter 方法 (ADO)
TOCTitle: CreateParameter method (ADO)
ms:assetid: cf080a0b-75d2-dcdf-2715-10af147358e9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250026(v=office.15)
ms:contentKeyID: 48547799
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231042
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: fa060811f60379e720e06be9f94e9403477c7869
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700680"
---
# <a name="createparameter-method-ado"></a>CreateParameter 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于创建具有指定属性的新 [Parameter](parameter-object-ado.md) 对象。

## <a name="syntax"></a>语法

**设置***参数* = *命令*。CreateParameter （*名称*、*类型*、 *Direction*、*大小*、*值*）

## <a name="return-value"></a>返回值

返回 **Parameter** 对象。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Name* |可选。 **字符串型** 值，包含 **Parameter** 对象的名称。|
|*Type* |可选。[DataTypeEnum](datatypeenum.md) 值，指定 **Parameter** 对象的数据类型。|
|*Direction* |可选。[ParameterDirectionEnum](parameterdirectionenum.md) 值，指定 **Parameter** 对象的类型。|
|*Size* |可选。 **长整型** 值，指定参数值的最大长度（字符或字节）。|
|*Value* |可选。 **变量型** 值，指定 **Parameter** 对象的值。|

## <a name="remarks"></a>备注

使用 **CreateParameter** 方法可以新建具有指定名称、类型、方向、大写和值的 **Parameter** 对象。在参数中传递的所有值都会写入相应的 **Parameter** 属性。

该方法并不会自动将 **Parameter** 对象追加到 **Command** 对象的 [Parameters](command-object-ado.md) 集合。这将允许您在将 **Parameter** 对象追加到集合时设置 ADO 将验证其值的附加属性。

如果在*Type*参数中指定的可变长度数据类型，您必须将*Size*参数传递或之前将其追加到**Parameters**集合; 设置**参数**对象的[Size](size-property-ado.md)属性否则，将发生错误。

如果在 *Type* 参数中指定数值数据类型（**adNumeric** 或 **adDecimal**），则还必须设置 [NumericScale](numericscale-property-ado.md) 和 [Precision](precision-property-ado.md) 属性。

