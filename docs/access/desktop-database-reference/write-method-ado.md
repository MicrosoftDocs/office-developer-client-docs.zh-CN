---
title: 编写方法-ActiveX 数据对象 (ADO)
TOCTitle: Write method (ADO)
ms:assetid: cabe4581-409f-7f05-bd59-d495bfb2c6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249986(v=office.15)
ms:contentKeyID: 48547697
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a04825a59f19b6b54fbb10652a1bba2fd0479588
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920961"
---
# <a name="write-method-ado"></a>Write 方法 (ADO)


**适用于**： Access 2013、 Office 2013


用于将二进制数据写入 [Stream](stream-object-ado.md) 对象。

## <a name="syntax"></a>语法

*流*。编写*缓冲区*

## <a name="parameters"></a>参数

  - *Buffer*

  - 包含要写入的字节数组的 **Variant** 。

## <a name="remarks"></a>备注

指定字节被写入 **Stream** 对象，且各字节之间不会插入空格。

当前 [Position](position-property-ado.md) 被设置为写入数据后的字节。 **Write** 方法不会将某个流中剩下的数据截断。如果希望截断这些字节，请调用 [SetEOS](seteos-method-ado.md)。

如果写入的数据超过了当前 [EOS](eos-property-ado.md) 位置，则 [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 的 **Size** 会增加，以包含所有新字节，并且 **EOS** 将移动到 **Stream** 中新的最后一个字节。


> [!NOTE]
> <P><STRONG>Write</STRONG> 方法用于二进制流（<A href="type-property-ado-stream.md">Type</A> 为 <STRONG>adTypeBinary</STRONG>）。对于文本流（<STRONG>Type</STRONG> 为 <STRONG>adTypeText</STRONG>），请使用 <A href="writetext-method-ado.md">WriteText</A>。</P>


