---
title: WriteText 方法 (ADO)
TOCTitle: WriteText method (ADO)
ms:assetid: 1ca2d9d5-11f4-d088-6fc3-53240208bb09
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248963(v=office.15)
ms:contentKeyID: 48543574
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 92983163a909e72c3da142ebcf63b7e0723e96af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308265"
---
# <a name="writetext-method-ado"></a>WriteText 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将指定的文本字符串写入 [Stream](stream-object-ado.md) 对象。

## <a name="syntax"></a>语法

*Stream*。WriteText*数据*,*选项*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Data* |**String** 值，包含要写入的字符文本。|
|*Options* |可选。[StreamWriteEnum](streamwriteenum.md) 值，指定是否必须在指定的字符串末尾写入行分隔符。|

## <a name="remarks"></a>注解

指定的字符串被写入 **Stream** 对象中，且每个字符串之间不会有任何用于分隔的空格或字符。

当前 [Position](position-property-ado.md) 被设置为写入数据后的字符处。 **WriteText** 方法不会将流中剩下的数据截断。如果希望截断这些字符，请调用 [SetEOS](seteos-method-ado.md)。

如果写入的数据超过了当前 [EOS](eos-property-ado.md) 位置，**Stream** 的 [Size](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 会增加，以包含所有新字符，并且 **EOS** 将移动到 **Stream** 中新的最后字节处。

> [!NOTE]
> **WriteText** 方法用于文本流（[Type](type-property-ado-stream.md) 为 **adTypeText**）。对于二进制流（**Type** 为 **adTypeBinary**），请使用 [Write](write-method-ado.md)。


