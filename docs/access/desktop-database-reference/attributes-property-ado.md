---
title: Attributes 属性 (ADO)
TOCTitle: Attributes property (ADO)
ms:assetid: 4cc1f036-606e-7d4b-d270-af374e9d99fa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249242(v=office.15)
ms:contentKeyID: 48544716
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231117
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 6495c70f64930e1b335c603f13e720ad581203a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296981"
---
# <a name="attributes-property-ado"></a>Attributes 属性 (ADO)


**适用于**：Access 2013、Office 2013


## <a name="attributes-property"></a>Attributes 属性

指示对象的一个或多个特征。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回 **Long** 值。

对于 [Connection](connection-object-ado.md) 对象， **Attributes** 属性为可读/写属性，其值可以为一个或多个 [XactAttributeEnum](xactattributeenum.md) 值的总和。默认值为零 (0)。

对于 [Parameter](parameter-object-ado.md) 对象， **Attributes** 属性为可读/写属性，其值可以为任何一个或多个 [ParameterAttributesEnum](parameterattributesenum.md) 值的总和。默认值为 **adParamSigned** 。

对于 [Field](field-object-ado.md) 对象， **Attributes** 属性可以为一个或多个 [FieldAttributeEnum](fieldattributeenum.md) 值的总和。该属性通常为只读属性。不过，对于追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，其 **Attributes** 属性仅在以下情况时为可读/写属性： [Field](value-property-ado.md) 的 **Value** 属性已指定，且新 **Field** 已由数据提供程序通过调用 [Fields](update-method-ado.md) 集合的 **Update** 方法成功添加。

对于 [Property](property-object-ado.md) 对象，**Attributes** 属性为只读属性，其值可以为任何一个或多个 [PropertyAttributesEnum](propertyattributesenum.md) 值的总和。

## <a name="remarks"></a>注解

使用 **Attributes** 属性可以设置或返回 **Connection** 对象、**Parameter** 对象、[Field](field-object-ado.md) 对象或 [Property](property-object-ado.md) 对象的各种特征。

设置多个属性 (attribute) 时，可以对相应的常量求和。如果将属性 (property) 值设置为包含相互不兼容的常量的总和，则将发生错误。

**远程数据服务使用情况**此属性在客户端**Connection**对象上不可用。

