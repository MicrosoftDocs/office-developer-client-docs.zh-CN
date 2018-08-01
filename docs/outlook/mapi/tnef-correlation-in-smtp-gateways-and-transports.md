---
title: SMTP 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 593f57d7-2891-40d1-a661-478a62d490ff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ec1d826ee2b3b46685a2c03dfaf45d2843869cc5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778982"
---
# <a name="tnef-correlation-in-smtp-gateways-and-transports"></a>SMTP 网关和传输中的 TNEF 相关性

  
  
**适用于**： Outlook 
  
网关和连接到 internet 的传输基于那些使用 SMTP、 MessageID SMTP 标题和**PR_TNEF_CORRELATION_KEY**属性的值用于实现 TNEF 相关的系统。 
  
出站消息的 MessageID 标头的值应为复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性，并且编码的 TNEF 流[attMAPIProps](attmapiprops.md)属性中。 请注意， **PR_TNEF_CORRELATION_KEY**二进制属性，而 MessageID 是字符串;null 终止符应包含在该副本和比较。 
  
将基于 MAPI 的消息系统连接到 Internet，例如 Microsoft Exchange Server 的所有 Microsoft 软件都使用此技术。 此方法应使用的任何 SMTP 网关和连接到为了最大限度地互操作性支持 MAPI 客户端的系统的传输。
  

