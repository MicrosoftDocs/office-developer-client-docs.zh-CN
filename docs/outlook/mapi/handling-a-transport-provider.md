---
title: 处理传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 60b3e5f4-4a9b-432f-bad4-4284225ab93f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0fe21cea26c956f8a03a51e2f302b040fc89e751
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416536"
---
# <a name="handling-a-transport-provider"></a>处理传输提供程序
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端通过传输提供程序和 MAPI 后台处理程序提供的状态对象与传输提供程序通信。 客户端通过调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 来检索状态表来访问状态对象。 Status 对象实现 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 接口，该接口具有用于配置提供程序、刷新传入和传出邮件队列、设置密码和状态验证的方法。 有关状态对象的信息，请参阅状态 [表和状态对象](status-table-and-status-objects.md)。


- [按需发送或接收邮件](sending-or-receiving-a-message-on-demand.md)：介绍如何按需发送或接收邮件。
    
- [设置传输顺序](setting-transport-order.md)：介绍如何设置传输顺序。
    
- [重新配置传输提供程序](reconfiguring-a-transport-provider.md)：介绍如何重新配置传输提供程序以及可以设置的属性。
    

