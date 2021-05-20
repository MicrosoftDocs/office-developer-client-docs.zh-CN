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
ms.openlocfilehash: 7e77c043e4f152740af9bdb2b8fb5b7bedece1c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430201"
---
# <a name="tnef-stream-structure"></a>TNEF 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
TNEF 流以 32 位签名开头，该签名将流标识为 TNEF 流。 签名后是一个 16 位无符号整数，用作跨引用附件到标记邮件文本中位置的键。 流的其余部分是 TNEF 属性序列。 邮件属性首先显示在 TNEF 流中，然后是附件属性。 属于特定附件的属性分组在一起，从 **attAttachRenddata** 属性开始。 
  
TNEF 流中使用的大多数常量值在 TNEF 中定义。H 头文件。 值得注意的是，TNEF_SIGNATURE、LVL_MESSAGE、LVL_ATTACHMENT和所有 TNEF 属性标识符都在此文件中定义。   其他常量具有由它们向 C 语言编译器解释的值。 通常，此类常量用于提供以下项目的大小。 例如 **， (ULONG**) 中的 sizeof 指示在 TNEF 流中的该位置应出现一个代表以下无符号长整型大小的整数。 
  
TNEF 流中所有整数以小尾二进制形式存储，但在此节以十六进制形式显示。 校验和值只是 16 位无符号整数，即校验和所应用的数据字节的总和，modulo 65536。 所有属性长度都是无符号长整型，包括任何终止 null 字符。
  
键是一个非零 16 位无符号整数，表示附件引用键的初始值。 附件引用键按顺序分配给每个附件，从使用 TNEF 的服务提供商传递给 [OpenTnefStream](opentnefstream.md) 函数的初始值开始。 服务提供商应为密钥生成随机的初始值，以最大程度地降低两条消息使用同一密钥的可能性。 
  
TNEF 实现使用属性标识符将属性映射到其相应的 MAPI 属性。 属性标识符是一个 32 位无符号整数，由两个单词值决定。 高顺序单词指示数据类型，如字符串或二进制，低顺序单词标识特定属性。 高顺序字词中的数据类型为：
  
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
   
每个属性的低顺序单词值在 TNEF 中定义。H 头文件。
  

