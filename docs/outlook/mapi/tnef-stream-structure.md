---
title: TNEF 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8eda1251-3858-4832-ac43-d817b4a7ea59
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0fcd1c79d1c0debfb18d270dc0e40de42842c6d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778992"
---
# <a name="tnef-stream-structure"></a>TNEF 流结构

  
  
**适用于**： Outlook 
  
TNEF 流开头的标识作为 TNEF 流流 32 位签名。 关注签名是一个 16 位无符号的整数，用作为键来交叉引用标记的消息文本中其位置的附件。 用于将 stream 的其余部分是 TNEF 属性的序列。 在 TNEF 流中，消息属性显示第一个和附件属性按照。 属于特定的附件属性分组在一起，开头**attAttachRenddata**属性。 
  
大部分 TNEF 流中使用的常量值 TNEF 中定义。H 头文件。 值得注意的是， **TNEF_SIGNATURE**、 **LVL_MESSAGE**、 **LVL_ATTACHMENT**和所有 TNEF 属性标识符是该文件中定义。 其他常量具有由其解释为 C 语言编译器的值。 通常情况下，此类常量用于为以下项的大小。 例如， **sizeof(ULONG)** 项目的定义中指示一个整数，表示的以下符号的长整数大小应进行中的 TNEF 流中该位置。 
  
TNEF stream 中的所有整数-little-endian 二进制格式存储，但十六进制整个本节中所示。 校验和值是只需 16 位无符号的整数的 sum、 模 65536 的字节数的校验和适用于数据。 所有属性长度都为无符号的长整数，包括任何 null 终止符。
  
密钥是表示附件引用键的初始值的非零值、 16 位无符号的整数。 附件引用键分配给每个附件按顺序开头的服务提供程序使用 TNEF 由传递给[OpenTnefStream](opentnefstream.md)函数的初始值。 服务提供商应生成随机初始值键大程度地减少两条消息，使用相同键的机会。 
  
TNEF 实现使用属性标识符属性映射到其对应的 MAPI 属性。 属性标识符是两个 word 值组成的 32 位无符号的整数。 高顺序单词指示的数据类型，如字符串或二进制，和低顺序单词标识的特定属性。 高位 word 中的数据类型包括：
  
|**类型**|**值**|
|:-----|:-----|
|atpTriples  <br/> |0x0000  <br/> |
|atpString  <br/> |0x0001  <br/> |
|atpText  <br/> |0x0002  <br/> |
|atpDate  <br/> |0x0003  <br/> |
|atpShort  <br/> |0x0004  <br/> |
|atpLong  <br/> |0x0005  <br/> |
|atpByte  <br/> |0x0006  <br/> |
|atpWord  <br/> |0x0007  <br/> |
|atpDword  <br/> |0x0008  <br/> |
|atpMax  <br/> |0x0009  <br/> |
   
每个属性的低序 word 值 TNEF 中定义。H 头文件。
  

