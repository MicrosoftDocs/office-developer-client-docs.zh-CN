---
title: 在 X 400 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e08f16ff60a282f1be3adf93d858471e38d19957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339625"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a>在 X 400 网关和传输中的 TNEF 相关性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
连接到基于 X. 400 的系统的网关和传输, 请使用 IM_THIS_IPM X. 400 属性的值和**attMessageID** TNEF 属性来实现 TNEF 关联。 
  
将出站邮件的 IM_THIS_IPM 属性的值复制到 TNEF 流中的**attMessageID** 。 IM_THIS_IPM X. 400 属性通常是一个字符串, 而**attMessageID** TNEF 属性是一个十六进制数字的字符串, 表示一个二进制值。 因此, IM_THIS_IPM X. 400 属性中的每个字符 (包括终止的 null 字符) 都必须转换为2个字符的十六进制字符串, 表示该字符的 ASCII 值。 例如, 如果 IM_THIS_IPM X. 400 属性为以下字符串: 
  
3030322D3030312D305337533A3A3936303631312D313533373030
  
然后, **attMessageID**的值将为以下十六进制数字序列: 
  
33 30 33 30 33 32 32 44
  
33 30 33 30 33 31 32 44
  
33 30 35 33 33 37 35 33
  
33 41 33 41 33 39 33 36
  
33 30 33 36 33 31 33 31
  
32 44 33 31 33 35 33 33
  
33 37 33 30 33 30 00
  
此技术由 Microsoft Exchange Server X 400 连接器使用。 此技术应由连接到 Microsoft Exchange Server 的任何 X 400 网关和传输使用, 以便最大限度地提高互操作性。
  
为了在将来和提供 Microsoft 软件时实现最大的兼容性, 还应将 IM_THIS_IPM X. 400 属性复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。 但是, 由于**PR_TNEF_CORRELATION_KEY**是二进制属性, 因此不需要转换为十六进制字符串。 
  

