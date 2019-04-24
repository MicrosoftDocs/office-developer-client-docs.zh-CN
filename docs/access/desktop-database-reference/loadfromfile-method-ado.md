---
title: LoadFromFile 方法 (ADO)
TOCTitle: LoadFromFile method (ADO)
ms:assetid: 33fd543f-bd24-9199-7540-2889b69221c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249107(v=office.15)
ms:contentKeyID: 48544123
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9316bc4302a559fa44082a0576595707157e9d64
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289883"
---
# <a name="loadfromfile-method-ado"></a>LoadFromFile 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将现有文件的内容加载到 [Stream](stream-object-ado.md) 中。

## <a name="syntax"></a>语法

*Stream*。LoadFromFile*文件名*

## <a name="parameters"></a>参数

|名称 |说明|
|:----|:----------|
|*FileName* |**字符串型**值，包含要加载到 **Stream** 中的文件的名称。*FileName* 可以包含 UNC 格式的任何有效的路径和名称。如果指定的文件不存在，将发生运行时错误。|

## <a name="remarks"></a>注解

可以使用该方法将本地文件的内容加载到 **Stream** 对象中。通过这种方式可以将本地文件的内容上载到服务器。

调用 **LoadFromFile** 之前， **Stream** 对象必须已经打开。该方法不会更改 **Stream** 对象的绑定；它将仍然绑定到由 URL 或最初用于打开 **Stream** 的 **Record** 指定的对象。

**LoadFromFile** 使用从文件读取的数据覆盖 **Stream** 对象的当前内容。 **Stream** 中的任何现有字节都被文件内容覆盖。 [LoadFromFile](eos-property-ado.md) 创建的 **EOS** 后面的任何以前存在的字节和剩余的字节都会被截去。

调用 **LoadFromFile** 之后，当前位置设置为 **Stream** 的开头（[Position](position-property-ado.md) 为 0）。

由于可能会向流的开头添加 2 个字节以进行编码，因此流大小与加载该流的文件的大小可能并不完全匹配。

