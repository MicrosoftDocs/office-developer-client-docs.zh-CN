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
  
所有使用 MAPI 库的客户端应用程序都必须调用 **MAPIInitialize** 函数。 有关详细信息，请参阅 [MAPIInitialize](mapiinitialize.md)。 **MAPIInitialize** 初始化会话的全局数据，并准备 MAPI 库以接受呼叫。 在某些情况下，有几个重要的标志需要设置： 
  
- MAPI_NT_SERVICE
    
    如果客户端MAPI_NT_SERVICE服务实现，请设置 Windows 标志。 如果你的客户端是Windows服务，并且未设置此标志，MAPI 将不会将它识别为服务。 
    
- MAPI_MULTITHREAD_NOTIFICATIONS
    
    the MAPI_MULTITHREAD_NOTIFICATIONS flag relates to how MAPI manages notifications. MAPI 创建一个隐藏窗口，该窗口在生成通知的对象发生更改时接收窗口消息。 此时将处理窗口消息，从而发送通知并调用相应的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 
    
- MAPI_NO_COINIT
    
    设置 MAPI_NO_COINT 标志，以便 **MAPIInitialize** 不会尝试使用对 [CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx)的调用初始化 COM。 如果将MAPIINIT_0传递到 **MAPIInitialize，** 并且 _ulFlags_ 设置为 MAPI_NO_COINIT，MAPI 将假定 COM 已初始化，并绕过对 **CoInitialize 的调用**。
    
如果未MAPI_MULTITHREAD_NOTIFICATIONS，MAPI 在用于第一个 **MAPIInitialize** 调用的线程上创建通知窗口。 MAPI 在单独的线程上创建通知窗口（如果MAPI_MULTITHREAD_NOTIFICATIONS一个专用于处理通知的线程）。 MAPI 期望用于创建隐藏通知窗口的线程： 
  
- 具有消息循环。
    
- 在会话的整个生命周期中保持未阻止状态。
    
- 生存期比客户端创建的其他线程长。 
    
可以通过设置第一个 **MAPIInitialize** 调用中的标记来选择使用哪个线程。 允许其中一个线程处理通知有一个危险，即如果线程消失，通知窗口将被破坏，并且通知无法再发送到任何其他线程。 此外，可能需要特殊处理来控制发送到隐藏窗口的邮件队列的通知邮件的调度。 
  
如果使用单独的窗口来处理通知，则确保通知将在适当的时间显示在适当的线程上。 不需要任何特殊代码来检查并处理Windows通知窗口的邮件。 
  
MAPI 建议以下类型的客户端应用程序使用单独的线程来创建隐藏的窗口，以用于通知支持：
  
- 所有多线程客户端。
    
- 单线程管理Windows Win32 控制台应用程序。
    
- 不需要使用主线程进行通知的单线程客户端。
    
若要使用单独的线程方法，请调用每个线程上的 **MAPIInitialize，** 并设置MAPI_MULTITHREAD_NOTIFICATIONS标志。 
  
> [!NOTE]
> 只有客户端首次调用 **MAPIInitialize** 会导致创建隐藏窗口以支持通知。 后续调用仅会导致引用计数递增。 
  

