---
title: Name 属性 (ADO)
TOCTitle: Name property (ADO)
ms:assetid: 4b19bd08-ac3c-86f0-471d-06a37a0d4f89
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249234(v=office.15)
ms:contentKeyID: 48544683
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f6fbfbd7008919cc4d784a4d0468d8471d102708
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288663"
---
# <a name="name-property-ado"></a>Name 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示对象的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个指示对象名称的 **String** 值。

## <a name="remarks"></a>注解

使用 **Name** 属性可指定名称或检索 **Command**、**Property**、**Field** 或 **Parameter** 对象的名称。

该值在 **Command** 对象上为可读/写，在 **Property** 对象上为只读。

对于 **Field** 对象， **Name** 通常为只读。然而，对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合的新 [Field](record-object-ado.md) 对象，只有在已指定 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序已通过调用 **Fields** 集合的 **Update** 方法成功添加新 [Field](update-method-ado.md) 之后， **Name** 才为可读/写。

对于尚未追加到 **Parameters** 集合的 [Parameter](parameters-collection-ado.md) ， **Name** 属性为可读/写属性。对于已追加的 **Parameter** 对象以及其他所有对象， **Name** 属性为只读属性。Names 在集合中不必唯一。

可以通过序号引用来检索对象的 **Name** 属性，然后可以直接通过名称引用该对象。 例如, 如果 rstMain (20)。名称产生了可更新性, 随后可以将此属性引用为可更新的结果, 随后可以将此属性引用为 rstMain ("可更新性")。

