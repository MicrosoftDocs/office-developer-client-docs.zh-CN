---
title: 读取方法-ActiveX 数据对象 (ADO)
TOCTitle: Read Method (ADO)
ms:assetid: 91c3ad34-f891-5be0-1fc1-c5c8a2ff07a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249641(v=office.15)
ms:contentKeyID: 48546357
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4fcc4c3039e1e55bb6bd33078542faa880d27ded
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466693"
---
# <a name="read-method-ado"></a>Read 方法 (ADO)


**适用于**： Access 2013 |Office 2013

可从二进制 [Stream](stream-object-ado.md) 对象读取指定数量的字节。

## <a name="syntax"></a>语法

*Variant* = *流*。读取 (*NumBytes* )

## <a name="parameters"></a>参数

  - *NumBytes*

  - 可选。 **长整型** 值，指定要从文件读取的字节数或 [StreamReadEnum](streamreadenum.md) 值 **adReadAll** ，后者为默认值。

## <a name="return-value"></a>返回值

**Read** 方法从 **Stream** 对象中读取指定数量的字节或整个流，并将结果数据以 **变量型** 格式返回。

## <a name="remarks"></a>备注

如果 *NumBytes* 大于 **Stream** 中剩余的字节数，则只返回剩余的字节，而不会为读取的数据填充任何内容来匹配 *NumBytes* 所指定的长度。如果没有字节可读取，则返回空值变量。**Read** 不能用来反向读取。


> [!NOTE]
> <P><EM>NumBytes</EM> 始终会计量字节数。对于 <STRONG>Stream</STRONG> 对象（<A href="type-property-ado-stream.md">Type</A> 为 <STRONG>adTypeText</STRONG>），请使用 <A href="readtext-method-ado.md">ReadText</A>。</P>


