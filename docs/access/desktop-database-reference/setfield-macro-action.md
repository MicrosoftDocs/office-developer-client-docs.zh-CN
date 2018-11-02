---
title: SetField 宏操作
TOCTitle: SetField macro action
ms:assetid: 66bd26e3-e8c3-b9a1-2f16-f29adc44a345
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195227(v=office.15)
ms:contentKeyID: 48545349
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d8ca2315a9a84000aa29b88043e4edea05ffb0ea
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922823"
---
# <a name="setfield-macro-action"></a>SetField 宏操作


**适用于**： Access 2013、 Office 2013

**SetField** 操作可用于向字段分配值。


> [!NOTE]
> <P>[!注释] <STRONG>SetField</STRONG> 操作仅适用于数据宏。</P>



## <a name="setting"></a>设置

下表列出了 **SetField** 操作的相关参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Name</strong></p></td>
<td><p>一个用于标识字段的字符串。</p></td>
</tr>
<tr class="even">
<td><p><strong>值</strong></p></td>
<td><p>一个表达式，指定要分配到的域的值。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

无法在 [**CreateRecord**](createrecord-data-block.md) 或 [**EditRecord**](editrecord-data-block.md) 数据块外部使用 **SetField** 操作。

