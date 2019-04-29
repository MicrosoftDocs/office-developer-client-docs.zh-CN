---
title: attOwner
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c6a4050-fd97-42ce-abb1-118254b367bd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 17e900ac28481388379133a95b4b206ca4bc1805
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427652"
---
# <a name="attowner"></a>attOwner

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**attOwner**属性被编码为端到端布局的计数字符串。 **attOwner**的格式如下所示: 
  
 **attOwner**: 
  
> 显示-名称-长度显示名称地址-长度_电子邮件地址_
    
 _电子邮件地址_
  
> 类型 **:** address 
    
与其他长度值不同, 显示名称-长度和地址长度是无符号的16位值, 而不是无符号长整数。 但是, 它们仍包括终止 null 字符。 _电子邮件地址_条目中的类型和地址字符串之间用文字冒号 (:)字符, 如 "smtp:joe@nowhere.com"。 仅组合类型 **:** 地址字符串以空值终止。
  
MAPI 属性到**attOwner**属性的映射取决于正在编码的邮件的邮件类。 
  

