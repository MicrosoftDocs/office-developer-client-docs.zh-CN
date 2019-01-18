---
title: CopyTo 方法 (ADO)
TOCTitle: CopyTo method (ADO)
ms:assetid: 1c1ab950-51f7-7ecc-ccd8-e689db02f06a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248958(v=office.15)
ms:contentKeyID: 48543558
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2e8de2caf2abc53b0dbd014f21a85a6d54749033
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717648"
---
# <a name="copyto-method-ado"></a>CopyTo 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于将 [Stream](type-property-ado-stream.md) 中指定数量的字符或字节（取决于 [类型](stream-object-ado.md)）复制到另一个 **Stream** 对象。

## <a name="syntax"></a>语法

*流*。CopyTo *DestStream* *NumChars*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*DestStream* |对象变量值，包含对打开的 **Stream** 对象的引用。当前 **Stream** 复制到由 *DestStream* 指定的目标 **Stream**。目标 **Stream** 必须已经打开。否则，将发生运行时错误。

<br/><br/>**注意**： *DestStream*参数可能无法**Stream**对象的代理，因为这将需要访问**Stream**对象的无法远程传输到客户端上的专用接口。|
|*NumChars* |可选。 **整型** 值，指定要从源 **Stream** 中的当前位置复制到目标 **Stream** 的字节或字符的数量。 默认值为-1，指定的所有字符或字节都复制从当前位置到[EOS](eos-property-ado.md)。|

## <a name="remarks"></a>备注

该方法从当前位置（由 [Position](position-property-ado.md) 属性指定）开始复制指定数量的字符或字节。 如果指定的数目超过了 **EOS** 之前的可用字节数，则仅复制从当前位置到 **EOS** 之间的字符或字节。 如果*NumChars*的值为-1，或被省略，复制所有字符或字节从当前位置开始。

如果目标流中已经有字符或字节，则复制内容末尾以外的所有内容将保留而不会被截去。 **Position** 成为紧跟在所复制的最后一个字节之后的字节。如果要截去这些字节，请调用 [SetEOS](seteos-method-ado.md)。

应使用 **CopyTo** 将数据复制到与源 **Stream** 类型相同的目标 **Stream** （它们的 **Type** 属性设置都为 **adTypeText** 或都为 **adTypeBinary**）。对于文本 **Stream** 对象，您可以将目标 **Stream** 的 [Charset](charset-property-ado.md) 属性设置更改为从一个字符集转换为另一个字符集。另外，文本 **Stream** 对象可以成功复制到二进制 **Stream** 对象中，但二进制 **Stream** 对象不能复制到文本 **Stream** 对象中。

