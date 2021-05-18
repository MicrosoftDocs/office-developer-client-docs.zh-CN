---
title: MAPI 中的事件通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7b3b625b-6dea-4b12-99a9-152935bdfe39
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 30d4ad5e0fc1ecdc4c8eb06f75d39e38dd481269
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321392"
---
# <a name="event-notification-in-mapi"></a>MAPI 中的事件通知

**适用于**：Outlook 2013 | Outlook 2016 
  
事件通知是两个 MAPI 对象之间的信息通信。 通过其中一个对象，客户端或服务提供商注册以通知可能在其他对象中发生的变化或错误（称为事件）。 事件发生后，第一个对象将收到更改或错误通知。 接收通知的对象称为通知接收器;负责通知的对象称为建议源。
  
建议接收器对象有三 (类型都是标准 MAPI 对象) ：
  
- 建议接收对象。   
- 窗体建议接收对象。  
- 查看通知接收对象。
    
建议接收对象是最常见的类型。 建议接收器通常由客户端应用程序实现，以接收通讯簿和消息存储通知并支持 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口。 **IMAPIAdviseSink** 包含单个方法 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)。 窗体和视图建议接收器不太常见;实现它们以接收有关自定义窗体更改的通知。 表单通知接收器支持 [IMAPIFormAdviseSink ： IUnknown](imapiformadvisesinkiunknown.md) 接口和视图通知接收器支持 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口。 由于大多数客户端都实现了标准建议接收对象，因此假定有关通知的讨论与通讯簿和邮件存储通知有关，而不是与窗体通知相关。 有关窗体通知详细信息，请参阅 [MAPI 窗体通知](mapi-forms-notifications.md) 和 [编写窗体服务器代码](writing-form-server-code.md)。
  
建议源对象由服务提供商和 MAPI 实现。 并非所有服务提供商都支持事件通知;它是可选的，但强烈建议使用。 邮件存储和通讯簿提供程序通常支持有关其多个对象的对象通知，并支持有关其内容和层次结构表的表通知。 传输提供程序不支持直接通知;它们依赖于与客户端通信的替代方法。
  
与通知接收器不同，建议源对象不是 MAPI 对象的唯一类型。 许多 MAPI 对象（如邮件存储和表）都可以扮演建议源的角色。 建议源是任何执行以下操作的 MAPI 对象：
  
- 实现 **用于接收通知** 注册的 Advise 方法。 
    
- 实现 **Unadvise** 方法以接收通知取消。 
    
- 向通过调用 **其 IMAPIAdviseSink：：OnNotify** 方法注册的适当建议接收对象生成相应类型的通知。 
    
实现通知接收对象的客户端在想要注册通知时调用 **Advise（** 在大多数情况下，传递应进行注册的对象的条目标识符）和 **Unadvise（** 当他们希望取消注册时）。 客户端向 Advise **传递** 一个参数，指示要监视几种类型的事件。 **Advise** 返回一个非零数，代表通知接收器与建议源之间的连接成功。 
  
在调用 **Advise** 之前，客户端可以通过检查邮件存储的 PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中是否设置了 STORE_NOTIFY_OK 标志来确定邮件存储提供程序是否支持通知。 客户端无法提前确定通讯簿提供程序是否支持通知。 客户端必须尝试注册，如果尝试失败，它们可以假定通知不受支持。
  
当客户端已注册的事件发生时，通知源会通过调用其 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法（其中包含事件相关信息的通知数据结构）通知通知接收者。 通知接收器的 **OnNotify** 实现可以执行任务以响应通知，例如更新内存中的数据或刷新屏幕显示。 
  
服务提供商可以手动实现对通知的支持，或利用以下三种 **IMAPISupport** 方法中提供的帮助 [：IMAPISupport：：Subscribe、IMAPISupport：：Unsubscribe](imapisupport-subscribe.md)和 [IMAPISupport：：Notify](imapisupport-notify.md)。 [](imapisupport-unsubscribe.md) Subscribe 和 **Unsubscribe** 方法处理提供程序的通知注册和取消注册;**Notify** 方法在适当时处理发送通知。 
  
若要使用支持对象方法进行通知注册，服务提供商会调用 [IMAPISupport：：Subscribe](imapisupport-subscribe.md) 的 **Advise** 方法，并传递到 **Subscribe** 通知接收器指针，客户端会传递给 **Advise**。 如果将条目标识符作为输入参数传递以指定建议源，服务提供商会将其转换为二进制密钥。 **Subscribe** 创建一个唯一的连接号码，服务提供商将返回此号码给客户端。 服务提供程序可以在 Advise 调用完成后随时释放客户端的建议接收对象指针。  
  
当客户端调用 **Unadvise** 以取消注册时，服务提供商会根据客户端的建议接收指针或调用 **Unsubscribe** 来缩小引用计数，以执行相同的操作。 
  
当生成通知时，服务提供商将执行与通知相关的任何内部处理，并初始化 [NOTIFICATION](notification.md) 结构，具体方法为将它所有未使用的成员都设置为零。 这种初始化 **NOTIFICATION** 结构的技术可帮助客户端创建更小、更快、更不容易出错的 **OnNotify** 实现。 
  
下图显示了通知接收器对象、建议源对象和 MAPI 之间的通信。 仅在建议源调用 **IMAPISupport** 方法进行通知支持时，才涉及 MAPI。 
  
**事件通知调用**
  
![事件通知调用](media/amapi_51.gif "事件通知调用")
  
MFCMAPI **CAdviseSink** 类 (AdviseSink.h 和 AdviseSink.cpp 文件) 对 Advise 的所有调用实现 advise 接收器 **对象**。 有关 MFCMAPI 的信息，请参阅[MFCMAPI 作为代码示例](mfcmapi-as-a-code-sample.md)和[MFCMAPI。](https://go.microsoft.com/fwlink/?LinkId=124154)
  

