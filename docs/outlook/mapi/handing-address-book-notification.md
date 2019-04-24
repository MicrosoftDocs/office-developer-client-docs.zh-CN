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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299501"
---
# <a name="handing-address-book-notification"></a>处理通讯簿通知
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿通知允许客户端了解对任何通讯簿条目或特定条目发生的事件。 您可以通过 MAPI 通讯簿注册这些通知, 方法是通过调用[IMAPITable:: advise](imapitable-advise.md), 通过使用[IAddrBook:: 建议](iaddrbook-advise.md)或通过通讯簿容器的层次结构或内容表。 
  
如果要为特定条目注册通知, 请指定通讯簿容器、通讯组列表或邮件用户的条目标识符, 如果在整个通讯簿上注册通知, 则指定 NULL。 条目标识符必须代表通讯簿容器中的邮件用户或通讯组列表。 **IAddrBook:: 建议**检查此条目标识符以确定哪个通讯簿提供程序负责相应的对象, 并将该呼叫转发到相应的通讯簿提供程序的[IABLogon:: Advise](iablogon-advise.md)方法。 
  
客户端可以在通讯簿条目上注册下列类型的事件:
  
- 严重错误
    
- 任何对象事件 (已创建、修改、删除、移动或复制)
    
- 修改的表
    
通常情况下, 仅在通讯簿容器内容和层次结构表上进行注册。 客户端很少使用低级邮件用户和通讯组列表对象进行注册。 这是因为:
  
- 许多通讯簿提供程序不支持其邮件用户和通讯组列表上的通知。
    
- 表通知足以用于跟踪更改并将其报告给用户。
    

