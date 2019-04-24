---
title: 初始化 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22ee8157-d74e-4a94-9c76-b9ac736d5211
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5fde3e7eda8d98eb5080fff360616649b1eb96a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309728"
---
# <a name="initializing-mapi"></a>初始化 MAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用 MAPI 库的所有客户端应用程序都必须调用**MAPIInitialize**函数。 有关详细信息, 请参阅[MAPIInitialize](mapiinitialize.md)。 **MAPIInitialize**为会话初始化全局数据, 并准备 MAPI 库以接受呼叫。 在某些情况下, 有一些非常重要的标志需要进行设置: 
  
- MAPI_NT_SERVICE
    
    如果您的客户端作为 Windows 服务实现, 则设置 MAPI_NT_SERVICE 标志。 如果你的客户端是 Windows 服务并且你不设置此标志, 则 MAPI 不会将其识别为服务。 
    
- MAPI_MULTITHREAD_NOTIFICATIONS
    
    MAPI_MULTITHREAD_NOTIFICATIONS 标志与 MAPI 管理通知的方式相关。 MAPI 创建一个隐藏窗口, 该窗口在生成通知的对象发生更改时接收窗口消息。 窗口消息在某一点进行处理, 从而导致发送通知并调用相应的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 
    
- MAPI_NO_COINIT
    
    设置 MAPI_NO_COINT 标志, 以便**MAPIInitialize**不会尝试使用[CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx)调用来初始化 COM。 如果将**MAPIINIT_0**结构传递到_ulFlags_设置为 MAPI_NO_COINIT 的**MAPIInitialize**中, MAPI 将假定 COM 已初始化, 并绕过**CoInitialize**调用。
    
如果未传递 MAPI_MULTITHREAD_NOTIFICATIONS 标志, MAPI 会在用于第一个**MAPIInitialize**呼叫的线程上创建通知窗口。 如果传递了 MAPI_MULTITHREAD_NOTIFICATIONS, MAPI 会在单独的线程上创建通知窗口, 这是一个专用于处理通知的线程。 MAPI 要求用来创建隐藏的通知窗口的线程执行以下操作: 
  
- 有一个消息循环。
    
- 在会话生命周期内保持不被阻止。
    
- 生存期比客户端创建的任何其他线程的生存期更长。 
    
您可以通过在第一个**MAPIInitialize**调用中设置标志来选择要使用哪个线程。 允许其中一个线程处理通知的危险在于, 如果线程消失了, 通知窗口将被破坏, 并且通知无法再发送到任何其他线程。 此外, 可能还需要进行特殊处理, 以控制发送到隐藏窗口的邮件队列的通知邮件的分派。 
  
如果使用单独的窗口处理通知, 请确保通知将在适当的时间出现在适当的线程上。 不需要任何特殊代码即可检查和处理发布到通知窗口的 Windows 消息。 
  
MAPI 建议以下类型的客户端应用程序使用单独的线程来创建用于通知支持的隐藏窗口:
  
- 所有多线程客户端。
    
- 单线程 Windows 服务和 Win32 控制台应用程序。
    
- 不需要使用其主线程进行通知的单线程客户端。
    
若要使用单独的线程方法, 请在每个线程上调用**MAPIInitialize** , 设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志。 
  
> [!NOTE]
> 仅客户端对**MAPIInitialize**的第一次调用会导致创建隐藏窗口以支持通知。 后续调用只会导致引用计数递增。 
  

