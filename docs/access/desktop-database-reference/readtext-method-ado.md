---
title: ReadText 方法 (ADO)
TOCTitle: ReadText method (ADO)
ms:assetid: 08f5bac4-dccd-696c-09a7-e1ba0cb38d79
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248826(v=office.15)
ms:contentKeyID: 48543108
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 883f74c06da83a46f9ffd1c30861d796c04b5c74
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699931"
---
# <a name="readtext-method-ado"></a>ReadText 方法 (ADO)

**适用于**： Access 2013、 Office 2013

可从文本 [Stream](stream-object-ado.md) 对象读取指定数量的字符。

## <a name="syntax"></a>语法

*字符串* = *流*。ReadText (*NumChars*)

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*NumChars* |可选。 **长整型** 值，指定要从文件读取的字符数或 [StreamReadEnum](streamreadenum.md) 值。默认值为 **adReadAll** 。|

## <a name="return-value"></a>返回值

**ReadText** 方法从 **Stream** 对象读取指定数量的字符、一整行或整个流，并返回结果字符串。

## <a name="remarks"></a>备注

如果 *NumChar* 大于流中剩余的字符数，则只返回剩余的字符，而不会为读取的字符串填充任何内容来满足 *NumChar* 所指定的长度。如果没有字符可读取，则返回空值变量。**ReadText** 不能用来反向读取。

> [!NOTE]
> **ReadText** 方法用于文本流（[Type](type-property-ado-stream.md) 为 **adTypeText**）。对于二进制流（**Type** 为 **adTypeBinary**），请使用 [Read](read-method-ado.md)。

