---
title: 快速关闭概述 （英文)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a7830d73-427c-4f8b-86f4-51e040c142c3
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: 17b1307427af2c35fe9ba8ee40dc78958e6b4a21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774897"
---
# <a name="fast-shutdown-overview"></a>快速关闭概述 （英文)

**适用于**： Outlook 
  
快速关闭是一种机制，MAPI 客户端启动的快速关闭通知与客户端有活动 MAPI 会话保存数据和设置在客户端进程退出之前的所有提供程序的客户端过程。 本主题介绍快速关闭的基本机制。 

启动 Microsoft Outlook 2010 中，现在包括 Microsoft Outlook 2013 MAPI 子系统提供[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。 Outlook 和其他 MAPI 客户端可以作为默认机制退出客户端进程采用快速关闭。 客户端计算机的 Windows 注册表中的用户级别设置控制采用快速关闭该计算机上的用户的所有 MAPI 客户端。 有关注册表设置的详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。
  
如果需要采用快速关闭 MAPI 客户端，它必须使用**IMAPIClientShutdown: IUnknown**接口。 下面是典型课程客户端尝试关闭时的事件： 
  
1. MAPI 客户端启动关闭通过调用[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法以确定是否 MAPI 子系统支持快速关闭。 
    
2. MAPI 子系统响应可用的快速关闭支持客户端的**IMAPIClientShutdown::QueryFastShutdown**呼叫通过使用以下过程： 
    
    1. MAPI 子系统在如果提供程序已实现与 MAPI 客户端进程具有活动的 MAPI 会话，每个 MAPI 提供程序调用[IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md)方法[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口。 
        
       > [!NOTE]
       >  MAPI 子系统始终查询，并通知通过 MAPI 提供程序**IMAPIProviderShutdown: IUnknown**中按以下顺序每个 MAPI 会话接口：
       > 1. 传输提供程序
       > 2. 通讯簿提供程序
       > 3. 存储提供程序 
    
    2. 根据客户端计算机上该用户的快速关闭注册表设置，MAPI 子系统指定相应到**IMAPIClientShutdown::QueryFastShutdown**的返回代码。 返回的代码是 S_OK 或 MAPI_E_NO_SUPPORT。
        
    3. MAPI 客户端调用[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)方法，以指示到 MAPI 子系统关闭的目的。 
        
    4. MAPI 子系统表示 MAPI 客户端将关闭每个加载 MAPI 提供程序。 已实现这些提供程序**IMAPIProviderShutdown: IUnknown**接口，MAPI 子系统调用相应的[IMAPIProviderShutdown::NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md)方法。 
        
    5. MAPI 客户端调用[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法向 MAPI 子系统指示客户端进程正在立即退出。 
        
    6. MAPI 子系统指示每个加载的 MAPI 提供程序，退出 MAPI 客户端进程。 已实现这些提供程序**IMAPIProviderShutdown: IUnknown**接口，MAPI 子系统调用相应的[IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md)方法。 此时，这些 MAPI 提供程序应验证所有必要的操作，如保存数据和设置，已完成在准备 MAPI 客户端立即断开连接的所有引用并退出。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
- [快速关闭用户选项](fast-shutdown-user-options.md)
- [快速关闭的最佳实践](best-practices-for-fast-shutdown.md)

