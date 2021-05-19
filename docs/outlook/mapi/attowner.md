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
  
**attOwner** 属性编码为倒数字符串，端到端布局。 **attOwner** 的格式如下所示： 
  
 **attOwner**： 
  
> display-name-length display-name address-length  _email-address_
    
 _email-address_
  
> type **：** address 
    
与其他长度值不同，display-name-length 和 address-length 是无符号 16 位值，而不是无符号长整型。 但是，它们仍包括以 null 字符结束。 电子邮件地址条目中的类型和地址字符串由文本冒号 (：) 字符分隔，如"smtp:joe@nowhere.com"。 只有组合类型 **：** 地址字符串以 null 结尾。
  
MAPI 属性到 **attOwner** 属性的映射取决于要编码的邮件的邮件类。 
  

