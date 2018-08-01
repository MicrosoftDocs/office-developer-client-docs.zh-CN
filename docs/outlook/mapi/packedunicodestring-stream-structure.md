---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2b4dcdcb50fb04410ed93940b46ea7a0d74fff41
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776579"
---
# <a name="packedunicodestring-stream-structure"></a>PackedUnicodeString 流结构

  
  
**适用于**： Outlook 
  
PackedUnicodeString 流结构包含 Unicode (utf-16) 字符串表示形式。 未通过空字符终止此字符串。 此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面列出的顺序。 存在的实际数据元素取决于中 utf-16 表示形式的字符串的长度。
  
- 一个字符串，其 utf-16 表示包含少于 255 个 WCHARs，数据要素如下所示：
    
  - 时长： 字节 （1 个字节），utf-16 字符串表示形式的长度，以 WCHARs，数。
    
  - 字符数： WCHAR 数组。 此数组的计数等于长度数据元素。 数组中的数据是 utf-16 字符串表示形式。
    
- 一个字符串，其 utf-16 表示包含 255 到 65535 WCHARs，数据要素如下所示：
    
  - 前缀： 字节 （1 个字节），255 之间的值 (0xff)。
    
  - 时长： 单词 （2 个字节），utf-16 字符串表示形式的长度，以 WCHARs，数。
    
  - 字符数： WCHAR 数组。 此数组的计数等于长度数据元素。 数组中的数据是 utf-16 字符串表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook 项和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

