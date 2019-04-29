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
  
TNEF 流以32位签名开头, 该签名将流标识为 TNEF 流。 签名之后是一个16位无符号整数, 用作在标记的邮件文本中对其位置进行交叉引用的附件的键。 流的其余部分是 TNEF 属性的序列。 邮件属性先出现在 TNEF 流中, 附件属性如下所示。 属于特定附件的属性会组合在一起, 从**attAttachRenddata**属性开始。 
  
tnef 流中使用的大部分常量值都是在 tnef 中定义的。H 头文件。 特别要注意的是, **TNEF_SIGNATURE**、 **LVL_MESSAGE**、 **LVL_ATTACHMENT**和所有 TNEF 属性标识符都是在此文件中定义的。 其他常量的值由其对 C 语言编译器的解释指示。 通常, 此类常量用于提供以下项的大小。 例如, 项的定义中的**sizeof (ULONG)** 表示在 TNEF 流中, 表示以下无符号长整数的大小的整数应出现在该位置。 
  
TNEF 流中的所有整数都存储在小 endian 二进制格式中, 但在此部分中显示为十六进制。 校验和值只是16位无符号整数, 它们是校验和应用于的数据字节的总和, 即模数65536。 所有属性长度均为无符号长整数, 包括任何终止的 null 字符。
  
键是一个非零的16位无符号整数, 它表示附件引用键的初始值。 将附件引用密钥分配给每个附件, 从以使用 TNEF 的服务提供程序传递给[OpenTnefStream](opentnefstream.md)函数的初始值开始, 依次为。 服务提供程序应生成密钥的随机初始值, 以最大限度地减少两个邮件使用相同密钥的机会。 
  
TNEF 实现使用属性标识符将属性映射到其对应的 MAPI 属性。 属性标识符是由两个单词值组成的32位无符号整数。 高序位字指示数据类型, 如字符串或二进制, 低序位字标识特定属性。 高序位字中的数据类型为:
  
|**Type**|**值**|
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
   
每个属性的低序位字值都是在 TNEF 中定义的。H 头文件。
  

