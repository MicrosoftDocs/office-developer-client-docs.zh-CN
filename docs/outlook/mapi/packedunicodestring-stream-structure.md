---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fc20c259f30ded2f96f3bf314e74207bebcac980
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348473"
---
# <a name="packedunicodestring-stream-structure"></a>PackedUnicodeString 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
PackedUnicodeString 流结构包含字符串的 Unicode (UTF-16) 表示形式。 此字符串不是由 null 字符终止的。 此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面列出的顺序后续。 现有的实际数据元素取决于 UTF-16 表示形式的字符串的长度。
  
- 对于其 UTF-16 表示形式包含小于 255 WCHARs 的字符串, 数据元素如下所示:
    
  - 长度: 字节 (1 个字节), 字符串的 utf-16 表示形式的长度 (以 WCHARs 为单位)。
    
  - 字符: WCHAR 数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 UTF-16 表示形式。
    
- 对于其 UTF-16 表示形式包含255到 65535 WCHARs 的字符串, 数据元素如下所示:
    
  - Prefix: BYTE (1 个字节), 值为 255 (0xff)。
    
  - length: WORD (2 个字节), 字符串的 utf-16 表示形式的长度 (以 WCHARs 为单位)。
    
  - 字符: WCHAR 数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 UTF-16 表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook 项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

