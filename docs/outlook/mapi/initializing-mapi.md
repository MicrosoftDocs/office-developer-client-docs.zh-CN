---
title: 初始化 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22ee8157-d74e-4a94-9c76-b9ac736d5211
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5f1dac712731175978bc639cc7296171448a41e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775956"
---
# <a name="initializing-mapi"></a>初始化 MAPI

  
  
**适用于**： Outlook 
  
使用 MAPI 库的所有客户端应用程序必须调用**MAPIInitialize**函数。 有关详细信息，请参阅[MAPIInitialize](mapiinitialize.md)。 **MAPIInitialize**会话初始化全局数据，并准备要接受呼叫的 MAPI 库。 有几个重要在某些情况下设置的标记： 
  
- MAPI_NT_SERVICE
    
    如果您的客户端实现作为 Windows 服务，请设置 MAPI_NT_SERVICE 标志。 如果您的客户端是一项 Windows 服务，并且未设置此标志，则 MAPI 不就将其视为服务。 
    
- MAPI_MULTITHREAD_NOTIFICATIONS
    
    MAPI 管理通知的方式与 MAPI_MULTITHREAD_NOTIFICATIONS 标志。 MAPI 创建生成通知对象发生变化时收到窗口消息隐藏的窗口。 此时，导致将通知发送和相应的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，调用处理窗口消息。 
    
- MAPI_NO_COINIT
    
    设置 MAPI_NO_COINT 标志，以便不会尝试通过调用[CoInitialize](http://msdn.microsoft.com/en-us/library/ms886303.aspx)初始化 COM **MAPIInitialize** 。 如果**MAPIINIT_0**结构与_ulFlags_设置为 MAPI_NO_COINIT 一起传递到**MAPIInitialize** ，MAPI 将假定 COM 已初始化和绕过**CoInitialize**调用。
    
MAPI 不传递 MAPI_MULTITHREAD_NOTIFICATIONS 标志，如果使用的线程上创建通知窗口的第一个**MAPIInitialize**呼叫。 MAPI 在如果传递 MAPI_MULTITHREAD_NOTIFICATIONS 单独的线程上创建通知窗口 — 线程专门处理通知。 MAPI 期望用于创建隐藏的通知窗口的主题： 
  
- 具有邮件循环。
    
- 保持取消整个生命周期中的会话。
    
- 具有比由您的客户端创建的任何其他线程较长的生存期。 
    
您可以选择使用哪个线程设置第一个**MAPIInitialize**调用中的标志。 在允许您线程处理通知之一危险是，如果线程消失，就会蒙受通知窗口，不再将通知发送给任何其他线程。 此外，可能需要特殊处理来控制发布到隐藏的窗口的消息队列的通知消息调度。 
  
如果您使用一个单独的窗口来处理通知，保证通知将显示在相应的线程上适当的时间。 您无需任何特殊代码以检查和处理发布到通知窗口 Windows 消息。 
  
MAPI 建议以下类型的客户端应用程序使用单独的线程创建通知支持隐藏窗口：
  
- 多线程的所有客户端。
    
- 单线程 Windows 服务和 Win32 控制台应用程序。
    
- 单线程的客户端不需要其主线程用于通知。
    
若要使用单独的线程方法，请对每个线程，设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志调用**MAPIInitialize** 。 
  
> [!NOTE]
> 仅客户端的第一次调用**MAPIInitialize**会创建支持通知隐藏的窗口。 后续调用仅原因引用计数递增。 
  

