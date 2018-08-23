---
title: 处理传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 60b3e5f4-4a9b-432f-bad4-4284225ab93f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00ae0f4be9818e0e9e4562784b4d5bf44eefe308
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567949"
---
# <a name="handling-a-transport-provider"></a>处理传输提供程序
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端与通过状态对象由传输提供程序和 MAPI 后台处理程序提供的传输提供程序进行通信。 客户端访问通过调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)检索状态表的状态的对象。 状态对象实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口，其中包含方法的配置提供程序、 刷新传入和传出消息队列、 设置密码和状态验证。 有关状态的对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。


- [发送或接收 on Demand 消息](sending-or-receiving-a-message-on-demand.md)： 介绍如何发送或接收按需型一条消息。
    
- [设置传输顺序](setting-transport-order.md)： 介绍如何设置传输顺序。
    
- [重新配置传输提供程序](reconfiguring-a-transport-provider.md)： 介绍如何重新配置的传输提供程序以及哪些属性可设置。
    

