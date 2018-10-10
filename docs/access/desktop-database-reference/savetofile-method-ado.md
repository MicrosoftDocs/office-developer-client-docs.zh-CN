---
title: SaveToFile 方法 (ADO)
TOCTitle: SaveToFile Method (ADO)
ms:assetid: db0fd95e-8ef3-af87-5346-8f8713153ca7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250104(v=office.15)
ms:contentKeyID: 48548097
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c0bd915a4eb6405b7d5ddd4bfe42eb4a98f68b89
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466135"
---
# <a name="savetofile-method-ado"></a>SaveToFile 方法 (ADO)


**适用于**： Access 2013 |Office 2013



可将 [Stream](stream-object-ado.md) 的二进制内容保存到文件。

## <a name="syntax"></a>语法

*流*。SaveToFile*文件名* *SaveOptions*

## <a name="parameters"></a>参数

  - *FileName*

  - **字符串型** 值，包含要保存 **Stream** 内容的文件的完全限定名称。可以保存到任意一个有效的本地位置或可通过 UNC 值访问的任意位置。

  - *SaveOptions*

  - [SaveOptionsEnum](saveoptionsenum.md) 值，指定 **SaveToFile** 是否应在文件不存在时创建新文件。默认值为 **adSaveCreateNotExists** 。通过这些选项，可以指定当指定文件不存在时引发错误。还可以指定 **SaveToFile** 覆盖现有文件的当前内容。


> [!NOTE]
> <P>[!注释] 如果覆盖现有文件（在设置 <STRONG>adSaveCreateOverwrite</STRONG> 时），则 <STRONG>SaveToFile</STRONG> 会从覆盖之前的原文件中截去新的 <A href="eos-property-ado.md">EOS</A> 之后的所有字节。</P>



## <a name="remarks"></a>备注

**SaveToFile** 可以用于将 **Stream** 对象的内容复制到本地文件。 **Stream** 对象的内容或属性都不会发生变化。在调用 **SaveToFile** 之前，必须打开 **Stream** 对象。

此方法不会更改 **Stream** 对象与其基础源之间的关联性。 **Stream** 对象将仍与打开时作为其来源的原始 URL 或 **Record** 相关联。

在 **SaveToFile** 操作之后，流中的当前位置（[Position 属性 (ADO)](position-property-ado.md)）设置为流的开头 (0)。

