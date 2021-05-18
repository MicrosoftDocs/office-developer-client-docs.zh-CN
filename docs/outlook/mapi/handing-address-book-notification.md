---
title: 处理通讯簿通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0dc4bb48-c8a1-447f-9e38-1c234a358fca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 122e50328272a4009e5a129233d449613817dfc8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413533"
---
# <a name="handing-address-book-notification"></a>处理通讯簿通知
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿通知允许客户端了解任何通讯簿条目或特定条目所发生事件。 可以通过调用 [IAddrBook：：Advise，](iaddrbook-advise.md) 或者通过通讯簿容器的层次结构或内容表（通过 [调用 IMAPITable：：Advise）通过 MAPI](imapitable-advise.md)通讯簿注册这些通知。 
  
如果要注册特定条目上的通知，请指定通讯簿容器、通讯组列表或邮件用户的条目标识符;如果注册整个通讯簿上的通知，则指定 NULL。 条目标识符必须表示通讯簿容器中的邮件用户或通讯组列表。 **IAddrBook：：Advise** 检查此条目标识符，以确定哪个通讯簿提供程序负责相应的对象，并转发对相应通讯簿提供程序 [的 IABLogon：：Advise](iablogon-advise.md) 方法的调用。 
  
客户端可以注册通讯簿条目上的以下类型的事件：
  
- 严重错误
    
- 创建、修改、 (、移动或复制的任何对象) 
    
- 已修改表
    
通常，仅对通讯簿容器内容和层次结构表进行注册。 客户端很少向较低级别的邮件用户和通讯组列表对象注册。 这是因为：
  
- 许多通讯簿提供程序不支持有关其邮件用户和通讯组列表的通知。
    
- 表通知足以跟踪更改并报告给用户。
    

