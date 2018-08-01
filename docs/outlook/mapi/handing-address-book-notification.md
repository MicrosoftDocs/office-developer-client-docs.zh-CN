---
title: 向通讯簿通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0dc4bb48-c8a1-447f-9e38-1c234a358fca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f198be78dd36a6d0c9439da68ab322cd8cfa4172
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775037"
---
# <a name="handing-address-book-notification"></a>向通讯簿通知
  
**适用于**： Outlook 
  
地址簿通知允许客户端若要了解到任何通讯簿条目或特定项所发生的事件。 您可以通过调用[IMAPITable::Advise](imapitable-advise.md)注册这些通知通过 MAPI 通讯簿通过调用[IAddrBook::Advise](iaddrbook-advise.md)或通过通讯簿容器层次结构或内容表。 
  
如果要在特定的条目和 NULL 上的通知注册的如果注册整个通讯簿上的通知，请指定通讯簿容器、 通讯组列表或消息的用户的项标识符。 消息的用户或通讯簿容器中的通讯组列表，则必须表示的项标识符。 **IAddrBook::Advise**检查此条目标识符来确定哪个地址簿提供程序负责为相应的对象，并将转发对相应的通讯簿提供程序的[IABLogon::Advise](iablogon-advise.md)方法的调用。 
  
客户端可以注册以下类型的通讯簿条目上的事件：
  
- 严重错误
    
- 任何对象事件 （创建、 修改、 删除、 移动或复制）
    
- 修改的表
    
通常，注册才会出现通讯簿容器内容和层次结构表。 很少客户端注册消息用户和通讯组列表对象的较低级别。 这是因为：
  
- 许多通讯簿提供程序不支持针对其消息的用户和通讯组列表的通知。
    
- 表通知是足以跟踪的更改并向他们报告给用户。
    

