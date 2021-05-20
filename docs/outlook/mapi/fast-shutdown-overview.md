---
title: 快速关闭概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a7830d73-427c-4f8b-86f4-51e040c142c3
description: 上次修改时间：2012 年 6 月 26 日
ms.openlocfilehash: 8c33214b04e7c41eab173196c09f145c20ddf219
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427204"
---
# <a name="fast-shutdown-overview"></a>快速关闭概述

**适用于**：Outlook 2013 | Outlook 2016 
  
快速关闭是 MAPI 客户端启动客户端进程快速关闭的机制，用于通知客户端具有活动 MAPI 会话的所有提供程序，以在客户端进程退出之前保存数据和设置。 本主题介绍快速关闭的基本机制。 

从 Microsoft Outlook 2010 开始，MAPI 子系统Microsoft Outlook 2013 [IMAPIClientShutdown ： IUnknown](imapiclientshutdowniunknown.md)接口。 Outlook MAPI 客户端可以采用快速关闭作为默认机制退出客户端进程。 客户端计算机的 Windows 注册表中的用户级别设置控制该计算机上该用户的所有 MAPI 客户端采用快速关闭。 有关注册表设置的详细信息，请参阅快速 [关闭用户选项](fast-shutdown-user-options.md)。
  
如果 MAPI 客户端需要采用快速关闭，则必须使用 **IMAPIClientShutdown ： IUnknown** 接口。 以下是客户端尝试关闭时的典型事件过程： 
  
1. MAPI 客户端通过调用 [IMAPIClientShutdown：：QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) 方法来确定 MAPI 子系统是否支持快速关闭来启动关闭。 
    
2. MAPI 子系统通过以下过程响应对客户端 **IMAPIClientShutdown：：QueryFastShutdown** 调用的可用快速关闭支持： 
    
    1. MAPI 子系统为 MAPI 客户端进程具有活动 MAPI 会话的每个 MAPI 提供程序调用 [IMAPIProviderShutdown：：QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) 方法（如果该提供程序已实现 [IMAPIProviderShutdown ： IUnknown](imapiprovidershutdowniunknown.md) 接口）。 
        
       > [!NOTE]
       >  MAPI 子系统始终按以下顺序通过每个 MAPI 会话中的 **IMAPIProviderShutdown ： IUnknown** 接口查询和通知 MAPI 提供程序：
       > 1. 传输提供程序
       > 2. 通讯簿提供程序
       > 3. 存储提供程序 
    
    2. 根据客户端计算机上该用户的快速关闭注册表设置，MAPI 子系统会向 **IMAPIClientShutdown：：QueryFastShutdown** 指定相应的返回代码。 返回代码可以是 S_OK 或 MAPI_E_NO_SUPPORT。
        
    3. MAPI 客户端调用 [IMAPIClientShutdown：：NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) 方法，向 MAPI 子系统指示要关闭的意图。 
        
    4. MAPI 子系统向每个加载的 MAPI 提供程序指示 MAPI 客户端将关闭。 对于已实现 **IMAPIProviderShutdown ： IUnknown** 接口的提供程序，MAPI 子系统调用相应的 [IMAPIProviderShutdown：：NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) 方法。 
        
    5. MAPI 客户端调用 [IMAPIClientShutdown：:D oFastShutdown](imapiclientshutdown-dofastshutdown.md) 方法，向 MAPI 子系统指示客户端进程即将退出。 
        
    6. MAPI 子系统向每个加载的 MAPI 提供程序指示 MAPI 客户端进程正在退出。 对于已实现 **IMAPIProviderShutdown ： IUnknown** 接口的提供程序，MAPI 子系统调用相应的 [IMAPIProviderShutdown：:D oFastShutdown](imapiprovidershutdown-dofastshutdown.md) 方法。 此时，这些 MAPI 提供程序应验证是否已完成所有必要的操作（如保存数据和设置）以准备 MAPI 客户端立即断开所有引用并退出。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
- [快速关闭用户选项](fast-shutdown-user-options.md)
- [快速关闭最佳做法](best-practices-for-fast-shutdown.md)

