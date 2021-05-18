---
title: SMTP 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 593f57d7-2891-40d1-a661-478a62d490ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0a685e081d319c43daa583d95d163677e81f2480
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413666"
---
# <a name="tnef-correlation-in-smtp-gateways-and-transports"></a>SMTP 网关和传输中的 TNEF 相关性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
连接到基于 Internet 的系统（即使用 SMTP 的系统）的网关和传输使用 MessageID SMTP 头和 **PR_TNEF_CORRELATION_KEY** 属性的值来实现 TNEF 关联。 
  
出站邮件的 MessageID 头的值应复制到 **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性，并采用 TNEF 流的 [attMAPIProps](attmapiprops.md) 属性进行编码。 请注意 **，PR_TNEF_CORRELATION_KEY** 是二进制属性，而 MessageID 是字符串;null 终止符应包含在副本和比较中。 
  
将基于 MAPI 的邮件系统连接到 Internet 的所有 Microsoft 软件（例如，Microsoft Exchange Server）。 为了最大限度地提高互操作性，连接到支持 MAPI 客户端的系统的任何 SMTP 网关和传输都应使用这种技术。
  

