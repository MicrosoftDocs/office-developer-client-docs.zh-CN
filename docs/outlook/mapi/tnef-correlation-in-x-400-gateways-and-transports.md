---
title: X.400 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 297fff3482a4b7aea391c3e1869cd127cc49cad2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566815"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a>X.400 网关和传输中的 TNEF 相关性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
网关和连接到基于 X.400 系统的传输使用 IM_THIS_IPM X.400 属性和**attMessageID** TNEF 属性的值来实现 TNEF 相关。 
  
出站消息的 IM_THIS_IPM 属性的值复制到**attMessageID** TNEF 流中。 IM_THIS_IPM X.400 属性通常是一个字符串， **attMessageID** TNEF 属性时十六进制数字表示的二进制值的字符串。 因此，必须在 IM_THIS_IPM X.400 属性中，包括终止空字符，每个字符转换为 2 个字符十六进制字符串表示该字符的 ASCII 值。 例如，如果 IM_THIS_IPM X.400 属性是以下字符串： 
  
3030322D3030312D305337533A3A3936303631312D313533373030
  
然后**attMessageID**的值采用十六进制数字的以下序列： 
  
33 30 33 30 33 32 32 44
  
33 30 33 30 33 31 32 44
  
33 30 35 33 33 37 35 33
  
33 41 33 41 33 39 33 36
  
33 30 33 36 33 31 33 31
  
32 44 33 31 33 35 33 33
  
33 37 33 30 33 30 00
  
Microsoft Exchange Server X.400 连接器使用此技术。 此方法应使用任何 X.400 网关和连接到 Microsoft Exchange Server 以最大限度地互操作性的传输。
  
为了与将来以及存在 Microsoft 软件的最大兼容，IM_THIS_IPM X.400 属性也应复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。 但是，由于**PR_TNEF_CORRELATION_KEY**是二进制属性，因此没有翻译十六进制字符串是必要的。 
  

