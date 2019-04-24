---
title: SaveToFile 方法 (ADO)
TOCTitle: SaveToFile method (ADO)
ms:assetid: db0fd95e-8ef3-af87-5346-8f8713153ca7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250104(v=office.15)
ms:contentKeyID: 48548097
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f3b08c9df435c7ce995a40af7b8ad5466b79245d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308923"
---
# <a name="savetofile-method-ado"></a>SaveToFile 方法 (ADO)

**适用于**：Access 2013、Office 2013

可将 [Stream](stream-object-ado.md) 的二进制内容保存到文件。

## <a name="syntax"></a>语法

*Stream*。SaveToFile*FileName*, *SaveOptions*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*FileName* |**字符串型** 值，包含要保存 **Stream** 内容的文件的完全限定名称。可以保存到任意一个有效的本地位置或可通过 UNC 值访问的任意位置。|
|*SaveOptions* |[SaveOptionsEnum](saveoptionsenum.md) 值，指定 **SaveToFile** 是否应在文件不存在时创建新文件。默认值为 **adSaveCreateNotExists** 。通过这些选项，可以指定当指定文件不存在时引发错误。还可以指定 **SaveToFile** 覆盖现有文件的当前内容。|

> [!NOTE]
> 如果覆盖现有文件（在设置 **adSaveCreateOverwrite** 时），则 **SaveToFile** 会从覆盖之前的原文件中截去新的 [EOS](eos-property-ado.md) 之后的所有字节。

## <a name="remarks"></a>注解

**SaveToFile** 可以用于将 **Stream** 对象的内容复制到本地文件。**Stream** 对象的内容或属性都不会发生变化。在调用 **SaveToFile** 之前，必须打开 **Stream** 对象。

此方法不会更改 **Stream** 对象与其基础源之间的关联性。 **Stream** 对象将仍与打开时作为其来源的原始 URL 或 **Record** 相关联。

在 **SaveToFile** 操作之后，流中的当前位置（[Position 属性 (ADO)](position-property-ado.md)）设置为流的开头 (0)。

