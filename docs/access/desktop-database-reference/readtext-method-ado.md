---
title: ReadText 方法 (ADO)
TOCTitle: ReadText Method (ADO)
ms:assetid: 08f5bac4-dccd-696c-09a7-e1ba0cb38d79
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248826(v=office.15)
ms:contentKeyID: 48543108
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5e4bc9febb76f71068517d2d83cddbdf4edee53b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891133"
---
# <a name="readtext-method-ado"></a>ReadText 方法 (ADO)


**适用于**： Access 2013、 Office 2013

可从文本 [Stream](stream-object-ado.md) 对象读取指定数量的字符。

## <a name="syntax"></a>语法

*字符串* = *流*。ReadText (*NumChars*)

## <a name="parameters"></a>参数

  - *NumChars*

  - 可选。 **长整型** 值，指定要从文件读取的字符数或 [StreamReadEnum](streamreadenum.md) 值。默认值为 **adReadAll** 。

## <a name="return-value"></a>返回值

**ReadText** 方法从 **Stream** 对象读取指定数量的字符、一整行或整个流，并返回结果字符串。

## <a name="remarks"></a>备注

如果 *NumChar* 大于流中剩余的字符数，则只返回剩余的字符，而不会为读取的字符串填充任何内容来满足 *NumChar* 所指定的长度。如果没有字符可读取，则返回空值变量。**ReadText** 不能用来反向读取。


> [!NOTE]
> <P><STRONG>ReadText</STRONG> 方法用于文本流（<A href="type-property-ado-stream.md">Type</A> 为 <STRONG>adTypeText</STRONG>）。对于二进制流（<STRONG>Type</STRONG> 为 <STRONG>adTypeBinary</STRONG>），请使用 <A href="read-method-ado.md">Read</A>。</P>


