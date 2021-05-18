---
title: X.400 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e08f16ff60a282f1be3adf93d858471e38d19957
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406372"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a>X.400 网关和传输中的 TNEF 相关性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
连接到基于 X.400 系统的网关和传输使用 IM_THIS_IPM X.400 属性的值和 **attMessageID** TNEF 属性的值来实现 TNEF 关联。 
  
出站IM_THIS_IPM的 IM_THIS_IPM 属性的值复制到 TNEF 流中的 **attMessageID。** X.400 IM_THIS_IPM X.400 属性通常是一个字符串，而 **attMessageID** TNEF 属性是一个代表二进制值的十六进制数字字符串。 因此，IM_THIS_IPM X.400 属性（包括终止 null 字符）中的每个字符都必须转换为表示该字符的 ASCII 值的 2 个字符的十六进制字符串。 例如，如果 IM_THIS_IPM X.400 属性是以下字符串： 
  
3030322D3030312D305337533A3A3936303631312D313533373030
  
那么 **attMessageID** 的值将是以下十六进制数字序列： 
  
33 30 33 30 33 32 32 44
  
33 30 33 30 33 31 32 44
  
33 30 35 33 33 37 35 33
  
33 41 33 41 33 39 33 36
  
33 30 33 36 33 31 33 31
  
32 44 33 31 33 35 33 33
  
33 37 33 30 33 30 00
  
此技术由 Microsoft Exchange Server X.400 Connector 使用。 为了最大限度地提高互操作性，连接到客户端的任何 X.400 网关和传输Microsoft Exchange Server此技术。
  
为了与未来以及当前 Microsoft 软件的最大兼容性，IM_THIS_IPM X.400 属性还应复制到 **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。 但是， **由于PR_TNEF_CORRELATION_KEY** 二进制属性，因此无需转换为十六进制字符串。 
  

