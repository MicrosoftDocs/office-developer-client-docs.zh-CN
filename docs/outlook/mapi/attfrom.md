---
title: attFrom
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2d405268-bb33-4863-be38-2d17e8fc956e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 496bd5439b9f004d3b13d2d73b31b5cac3f9eec9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432413"
---
# <a name="attfrom"></a>attFrom

**适用于**：Outlook 2013 | Outlook 2016 
  
**attFrom** 属性编码为 **TRP** 结构，该结构对发件人的 显示名称 和电子邮件地址进行编码，后跟发件人的 显示名称 和地址，然后是任何必要的填充。 **attFrom 的格式** 如下所示： 
  
**attFrom**： _TRP-structure_ sender-display-name _ sender-address _ padding 
    
sender-display-name 是一个以 null 结尾的字符串，如有必要，该字符串会填充一个额外的 null 字符，以达到 2 字节的边界。 **attFrom** 编码末尾的填充由达到 **TRP** 边界大小所需的 (null) 组成。 
  
_TRP-structure：trpidOneOff_  cbgrtrp cch cb 
    
对于 **attFrom** 项 **，TRP**-structure 始终是一次一次编码，因此 **TRP**-structure 字段的 trpid 始终为 **trpidOneOff**。 cbgrtrp、cch 和 cb 项对应于 **TRP** 结构的其余字段。 
  
cbgrtrp 字段的计算公式为 (**sizeof (TRP) \* 2) 、** 以 null 终止的 sender-display-name 的长度及其填充以及以 null 终止的发件人地址的长度。
  
cch 字段的计算公式为具有填充的以 null 终止的显示名称的长度。
  
cb 字段的计算公式为以 null 终止的发件人地址的长度。
  
_sender-address：_ address-type **：** address **'\0'**
    
发件人地址是一个字符串，由四个部分组成：地址类型、文本冒号 (：) 、地址本身和终止 null 字符。 例如，字符串 `fax:1-909-555-1234\0` 将是合法发件人地址值。
  

