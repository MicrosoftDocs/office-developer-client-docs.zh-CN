---
title: attFrom
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2d405268-bb33-4863-be38-2d17e8fc956e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c7c0d1df32a0ad6359fad20128a6a1e3dd225143
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774594"
---
# <a name="attfrom"></a>attFrom

**适用于**： Outlook 
  
**AttFrom**属性被编码为**TRP**结构，它将编码的发件人后, 跟的显示名称和发件人后, 跟任何必要的填充的地址的显示名称和电子邮件地址。 **AttFrom**的格式如下所示： 
  
**attFrom**: _TRP 结构_发件人显示名称 _ 发件人地址 _ 边距 
    
发件人显示名称是以 null 结尾的字符串填充了其他空字符，如有必要，以到达 2 字节边界。 **AttFrom**编码的末尾的空白包含尽可能多的 null 字符，根据需要到达**sizeof(TRP)** 边界。 
  
_TRP 结构：_**trpidOneOff** cbgrtrp cch cb 
    
对于**attFrom**项， **TRP**-结构是始终一次性编码，因此关闭**TRP**trpid-结构字段总是**trpidOneOff**。 Cbgrtrp、 cch 和 cb 项目对应于**TRP**结构的剩余字段。 
  
Cbgrtrp 字段的计算公式为的总和 **(sizeof(TRP) \*2)**，名称的长度 null 结尾发件人-显示-具有其填充和 null 结尾发件人的地址的长度。
  
Cch 字段的计算公式为具有其填充 null 结尾显示名称的长度。
  
Cb 字段的计算公式为 null 结尾发件人的地址的长度。
  
_发件人地址：_ 地址类型： **:** 地址**\0**
    
发件人地址是一个字符串，其中包含四个部分、 地址类型、 文字冒号 （:）、 本身的地址和终止空字符。 例如，字符串`fax:1-909-555-1234\0`是一个合法发件人地址值。
  

