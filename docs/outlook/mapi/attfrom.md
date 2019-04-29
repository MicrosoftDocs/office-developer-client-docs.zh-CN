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
  
**attFrom**属性被编码为**TRP**结构, 该结构对发件人的显示名称和电子邮件地址进行编码, 后跟发件人的显示名称和地址, 后跟任何必需的填充。 **attFrom**的格式如下所示: 
  
**attFrom**: _TRP-结构_发件人-显示名称 _ 发件人-地址 _ 填充 
    
发件人-显示名称是以 null 结尾的字符串, 如果需要, 使用额外的 null 字符填充, 以达到2字节边界。 **attFrom**编码结尾的边距由所需的任意多个 null 字符组成, 以达到**sizeof (TRP)** 边界。 
  
_TRP:_**trpidOneOff** cbgrtrp cch cb 
    
对于**attFrom**项, **TRP**始终是一次性编码, 因此**TRP**结构字段的 trpid 始终为**trpidOneOff**。 cbgrtrp、cch 和 cb 项目对应于**TRP**结构的其余字段。 
  
cbgrtrp 字段的计算公式为 **(sizeof (TRP \*) 2)**、以 null 结尾的发件人的显示名称的填充长度以及以 null 结尾的发件人地址的长度。
  
cch 字段是以以 null 结尾的显示名称的长度作为填充的长度计算的。
  
cb 字段作为以空值终止的发件人地址的长度计算。
  
_发件人-地址:_ 地址-类型 **:** 地址 **"\ 0"**
    
发件人地址是一个字符串, 由四部分组成: 地址类型、文本冒号 (:)、地址本身以及终止 null 字符。 例如, 字符串`fax:1-909-555-1234\0`将是合法的发件人地址值。
  

