---
title: Stream 对象 (ADO)
TOCTitle: Stream Object (ADO)
ms:assetid: d49b1514-e0b4-0aca-d5c2-8266f3f4fe65
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250065(v=office.15)
ms:contentKeyID: 48547945
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d689e853f1104305a08c1193b098d99935035092
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467848"
---
# <a name="stream-object-ado"></a>Stream 对象 (ADO)


**适用于**： Access 2013 |Office 2013

代表二进制数据流或文本流。

## <a name="remarks"></a>说明

在文件系统或电子邮件系统等树状分层结构中，[Record](record-object-ado.md) 可能具有与其关联的默认二进制位流，其中包含文件或电子邮件的内容。 **Stream** 对象可以用来处理包含这些数据流的字段或记录。可以通过以下方式获得 **Stream** 对象：

  - 从指向包含二进制数据或文本数据的对象（通常为文件）的 URL 获得。该对象可以是简单文档、表示结构化文档的 **Record** 对象或文件夹。

  - 通过打开与 **Record** 对象关联的默认 **Stream** 对象获得。打开 **Record** 对象时，您可以获得与 **Record** 对象关联的默认流，以免除仅为打开默认流所需的往返行程。

  - 通过实例化 **Stream** 对象获得。使用这些 **Stream** 对象可存储用于应用程序的数据。与那些与 URL 关联的 **Stream** 或 **Record** 的默认 **Stream** 不同，实例化的 **Stream** 默认情况下与基础源没有任何关联。

使用 **Stream** 对象的方法和属性，可以执行下列操作：

  - 使用 **Open** 方法通过 **Record** 或 URL 打开 [Stream](open-method-ado-stream.md) 对象。

  - 使用 **Close** 方法关闭 [Stream](close-method-ado.md) 。

  - 使用 **Write** 和 [WriteText](write-method-ado.md) 方法向 [Stream](writetext-method-ado.md) 输入字节或文本。

  - 使用 **Read** 和 [ReadText](read-method-ado.md) 方法从 [Stream](readtext-method-ado.md) 读取字节。

  - 使用 **Flush** 方法将仍在 ADO 缓冲区中的任何 [Stream](flush-method-ado.md) 数据写入基础对象。

  - 使用 **CopyTo** 方法将一个 **Stream** 中的内容复制到其他 [Stream](copyto-method-ado.md) 中。

  - 使用 [SkipLine](skipline-method-ado.md) 方法和 [LineSeparator](lineseparator-property-ado.md) 属性控制从源文件读取行的方式。

  - 使用 [EOS](eos-property-ado.md) 属性和 [SetEOS](seteos-method-ado.md) 方法确定流的末尾位置。

  - 使用 [SaveToFile](savetofile-method-ado.md) 和 [LoadFromFile](loadfromfile-method-ado.md) 方法保存和还原文件中的数据。

  - 使用 **Charset** 属性指定用于存储 [Stream](charset-property-ado.md) 的字符集。

  - 使用 **Cancel** 方法中止异步 [Stream](cancel-method-ado.md) 操作。

  - 使用 **Size** 属性确定 [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 中的字节数。

  - 使用 **Position** 属性控制 [Stream](position-property-ado.md) 中的当前位置。

  - 使用 **Type** 属性确定 [Stream](type-property-ado-stream.md) 中的数据类型。

  - 使用 **State** 属性确定 [Stream](state-property-ado.md) 的当前状态（关闭、打开和正在执行）。

  - 使用 **Mode** 属性指定 [Stream](mode-property-ado.md) 的访问模式。


> [!NOTE]
> <P>[!注释] 使用 http 方案的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对和相对 URL</A>。</P>


