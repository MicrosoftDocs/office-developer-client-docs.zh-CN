---
title: attSentFor
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aa8c8d64-d2a0-4cdf-a8aa-21c8d0a0a3fc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f961348e7be474202273aa97a2922566ef40c3a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408836"
---
# <a name="attsentfor"></a>attSentFor

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**attSentFor** 属性编码为端到端布局的计数字符串。 **attSentFor 的格式** 如下所示： 
  
 **attSentFor**： 
  
> display-name-length display-name address-length  _email-address_
    
 _email-address_
  
> type **：** address 
    
与其他长度值不同，display-name-length 和 address-length 是无符号 16 位值，而不是无符号长整型。 但是，它们仍包括以 null 字符结束。 电子邮件地址条目中的类型和地址字符串由文本冒号 (：) 字符分隔，如"smtp:joe@nowhere.com"。 只有组合类型 **：** 地址字符串以 null 结尾。
  

