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
  
事件通知是两个 MAPI 对象之间的信息通信。 通过其中一个对象, 客户端或服务提供程序注册发生更改或错误的通知 (称为事件), 该事件可能发生在其他对象中。 事件发生后, 会向第一个对象通知更改或错误。 接收通知的对象称为 "通知接收器";负责通知的对象称为 "建议源"。
  
有三种类型的通知接收器对象 (所有类型都是标准 MAPI 对象):
  
- 通知接收器对象。   
- 表单建议接收器对象。  
- 查看建议接收器对象。
    
建议接收器对象是最常见的类型。 建议接收器通常由客户端应用程序实现, 以接收通讯簿和邮件存储通知, 并支持[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口。 **IMAPIAdviseSink**包含一个方法, [IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)。 窗体和视图的建议接收器不常见;它们的实现是为了接收有关自定义窗体更改的通知。 表单建议接收器支持[IMAPIFormAdviseSink: iunknown](imapiformadvisesinkiunknown.md)接口, 查看建议接收器支持[IMAPIViewAdviseSink: iunknown](imapiviewadvisesinkiunknown.md)接口。 由于大多数客户端都实现标准的建议接收器对象, 因此假定讨论通知与通讯簿和邮件存储通知有关, 而不是表单通知。 有关表单通知的详细信息, 请参阅[MAPI 表单通知](mapi-forms-notifications.md)和[编写表单服务器代码](writing-form-server-code.md)。
  
通知源对象由服务提供商和 MAPI 实现。 并非所有服务提供程序都支持事件通知;它是可选的, 但强烈建议这样做。 邮件存储和通讯簿提供程序通常支持其内容和层次结构表上的多个对象和表通知的对象通知。 传输提供程序不直接支持通知;它们依赖于与客户端进行通信的替代方法。
  
与建议接收器不同, 建议源对象不是 MAPI 对象的唯一类型。 许多 MAPI 对象 (如邮件存储和表) 可以承担建议源的角色。 "建议源" 是执行以下操作的任何 MAPI 对象:
  
- 实现用于接收通知注册的**建议**方法。 
    
- 实现**Unadvise**方法以接收通知取消。 
    
- 通过调用**IMAPIAdviseSink:: OnNotify**方法, 向已注册的相应通知接收器对象生成适当类型的通知。 
    
实现通知接收器对象的客户端在想要注册通知时调用**建议**, 在大多数情况下, 在应进行注册的对象的条目标识符中传递, 并在需要时使用**Unadvise**来取消注册. 客户端将一个参数传递给 "**建议**", 指示他们要监视的几种类型的事件中的哪一种。 **建议**返回一个非零的数字, 表示通知接收器和通知源之间的成功连接。 
  
在调用**Advise**之前, 客户端可以通过检查邮件存储提供程序的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中是否设置了 STORE_NOTIFY_OK 标志来确定邮件存储提供程序是否支持通知财产. 客户端无法提前确定某个通讯簿提供程序是否支持通知。 客户端必须尝试注册, 如果尝试失败, 则可以假定通知不受支持。
  
在已注册客户端的事件发生时, 建议源通过调用其[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 并使用包含有关事件的信息的通知数据结构来通知通知接收器。 通知接收器的**OnNotify**实现可以执行任务以响应通知, 例如更新内存中的数据或刷新屏幕显示。 
  
服务提供程序可以手动实现对通知的支持, 也可以利用三个**IMAPISupport**方法提供的帮助: [IMAPISupport:: 订阅](imapisupport-subscribe.md)、 [IMAPISupport:: 退订](imapisupport-unsubscribe.md)和[IMAPISupport:: Notify](imapisupport-notify.md). **订阅**和**取消订阅**方法处理提供程序的通知注册和注销;**Notify**方法处理在适当的时候发送通知。 
  
若要将支持对象方法用于通知注册, 服务提供程序将调用[IMAPISupport:: 订阅](imapisupport-subscribe.md)其**建议**方法, 并**** 传递给客户端传递给**建议**的建议接收器指针。 如果条目标识符作为输入参数传递, 以指定建议源, 则服务提供程序会将其转换为二进制密钥。 **订阅**创建唯一的连接号码, 该号码是服务提供商返回给客户端的号码。 在**通知**调用完成后, 服务提供商可以随时释放客户端的建议接收器对象指针。 
  
当客户端调用**Unadvise**以取消注册时, 服务提供程序可以将客户端的建议接收器指针上的引用计数减一, 或者呼叫**取消订阅**以执行相同的操作。 
  
当需要生成通知时, 服务提供商将执行任何与通知相关的内部处理, 并通过将其未使用的所有成员设置为零来初始化[通知](notification.md)结构。 这种初始化**通知**结构的技术可以帮助客户端创建更小、更快速且不易出错的**OnNotify**实现。 
  
下图显示了通知接收器对象、通知源对象和 MAPI 之间的通信。 仅当通知源调用**IMAPISupport**方法以获取通知支持时, 才会涉及 MAPI。 
  
**事件通知调用**
  
![事件通知调用](media/amapi_51.gif "事件通知调用")
  
MFCMAPI **CAdviseSink**类 (使用 AdviseSink 和 AdviseSink 文件) 实现了所有调用的建议接收器对象。 **** 有关 MFCMAPI 的详细信息, 请参阅[MFCMAPI 作为代码示例](mfcmapi-as-a-code-sample.md)和[MFCMAPI](https://go.microsoft.com/fwlink/?LinkId=124154)。
  

