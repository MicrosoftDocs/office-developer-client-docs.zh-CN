---
title: 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4fa47824-b4ef-41e1-9096-c1b1cdacd7ac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 68a842ccfdaea8ecdb975e1c510711b0e43fd576
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778711"
---
# <a name="sending-a-message"></a>发送邮件

  
  
**适用于**： Outlook 
  
当您准备要发送消息时，调用其[IMessage::SubmitMessage](imessage-submitmessage.md)方法。 **SubmitMessage**传出队列中放置邮件和消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_SUBMIT 标志。
  
消息存储提供程序，如果紧密耦合到传输提供程序，则将直接向其传递到邮件系统的传输邮件。 如果不紧密耦合的消息存储提供程序通知传出队列已更改 MAPI 后台处理程序和 MAPI 后台处理程序将邮件传输到适当的传输提供程序。
  
如果允许用户取消发送操作，请调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)来实现此功能。 **AbortSubmit**传出队列中删除邮件。 可以允许用户停止从最新动态直到消息提供给基础邮件系统发送。 
  
如果**SubmitMessage**返回 MAPI_E_CORRUPT_DATA，假定正在发送的数据是否立即丢失。 尝试发送第二次之前, 重新通过调用[IMAPIProp::SetProps](imapiprop-setprops.md)和[IMAPIProp::SaveChanges](imapiprop-savechanges.md)编写邮件。 如果这些**IMAPIProp**呼叫失败或**SubmitMessage**失败第二次向用户显示错误。 
  
成功调用**SubmitMessage**之后, 释放已分配给的收件人列表的任何内存和释放邮件及其附件。 已发送一条消息，一旦 MAPI 不允许这些对象的指针上任何进一步的操作。 一个例外调用**IUnknown::Release**。 允许没有任何其他呼叫，因为许多消息存储提供程序使失效的已发送邮件的项标识符。
  

