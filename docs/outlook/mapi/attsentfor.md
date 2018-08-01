---
title: attSentFor
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aa8c8d64-d2a0-4cdf-a8aa-21c8d0a0a3fc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fd7f79ad7a36fd174bf9817ff463b00e6a334104
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774608"
---
# <a name="attsentfor"></a>attSentFor

  
  
**适用于**： Outlook 
  
为盘点的字符串分布的端到端编码**attSentFor**属性。 **AttSentFor**的格式如下所示： 
  
 **attSentFor**: 
  
> 显示名称长度显示名称地址长度_电子邮件地址_
    
 _电子邮件地址_
  
> 类型： **:** 地址 
    
与其他长度不同值、 显示名称长度和地址长度是无符号的 16 位值，而不是无符号的长整数。 它们仍包括但是终止 null 字符。 使用原义冒号 （:） 字符，例如"smtp:joe@nowhere.com"分隔中的_电子邮件地址_条目的类型和地址字符串。 合并的类型： **:** 的地址字符串以 null 结尾。
  

