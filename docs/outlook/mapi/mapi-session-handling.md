---
title: MAPI 会话处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3bc4aea5-ab01-4ba5-a4ad-7a9a76c6bf55
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cdf3052175870287ff1a66d3745e90f8b8fff256
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776325"
---
# <a name="mapi-session-handling"></a>MAPI 会话处理

  
  
**适用于**： Outlook 
  
您可以与服务提供商和基础消息系统通信之前，必须建立一个会话。 MAPI 会话是其他 MAPI 组件从客户端的链接。 成功启动会话的结果，MAPI 返回到客户端会话对象的指针 — 实现**IMAPISession**接口的对象。 有关详细信息，请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。 **IMAPISession**接口的方法可用于访问通讯簿和消息存储提供程序的对象、 访问多个表、 显示表单、 设置传输提供程序属性和执行配置文件和消息服务管理。 
  
## <a name="in-this-section"></a>本节内容

[启动 MAPI 会话](starting-a-mapi-session.md)
  
> 介绍如何启动 MAPI 会话，并包括具有更多详细信息的主题的链接。
    
[结束 MAPI 会话](ending-a-mapi-session.md)
  
> 介绍如何结束 MAPI 会话。
    
[使用会话访问对象](accessing-objects-by-using-the-session.md)
  
> 介绍如何使用会话指针访问会话对象。
    
[检索主要标识和提供程序标识](retrieving-primary-and-provider-identity.md)
  
> 介绍用于检索主属性和提供程序的标识。
    
[状态表和状态对象](status-table-and-status-objects.md)
  
> 介绍如何访问状态表中的信息。
    

