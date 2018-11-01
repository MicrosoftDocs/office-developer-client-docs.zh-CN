---
title: LoadFromFile 方法 (ADO)
TOCTitle: LoadFromFile Method (ADO)
ms:assetid: 33fd543f-bd24-9199-7540-2889b69221c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249107(v=office.15)
ms:contentKeyID: 48544123
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 61244e989815d5c4ba1943e61aea7f6a6abf139d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872030"
---
# <a name="loadfromfile-method-ado"></a>LoadFromFile 方法 (ADO)


**适用于**： Access 2013、 Office 2013



用于将现有文件的内容加载到 [Stream](stream-object-ado.md) 中。

## <a name="syntax"></a>语法

*流*。LoadFromFile*文件名*

## <a name="parameter"></a>参数

  - *FileName*

  - **字符串型** 值，包含要加载到 **Stream** 中的文件的名称。 *FileName*可以包含任何有效路径和名称采用 UNC 格式。 如果指定的文件不存在，将发生运行时错误。

## <a name="remarks"></a>备注

可以使用该方法将本地文件的内容加载到 **Stream** 对象中。通过这种方式可以将本地文件的内容上载到服务器。

调用 **LoadFromFile** 之前， **Stream** 对象必须已经打开。该方法不会更改 **Stream** 对象的绑定；它将仍然绑定到由 URL 或最初用于打开 **Stream** 的 **Record** 指定的对象。

**LoadFromFile** 使用从文件读取的数据覆盖 **Stream** 对象的当前内容。 **Stream** 中的任何现有字节都被文件内容覆盖。 [LoadFromFile](eos-property-ado.md) 创建的 **EOS** 后面的任何以前存在的字节和剩余的字节都会被截去。

调用 **LoadFromFile** 之后，当前位置设置为 **Stream** 的开头（[Position](position-property-ado.md) 为 0）。

由于可能会向流的开头添加 2 个字节以进行编码，因此流大小与加载该流的文件的大小可能并不完全匹配。

