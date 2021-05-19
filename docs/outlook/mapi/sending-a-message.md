---
title: 发送信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4fa47824-b4ef-41e1-9096-c1b1cdacd7ac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 01fd66033da0f24948913f47a752d555eca655fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423620"
---
# <a name="sending-a-message"></a>发送信息

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备好发送邮件时，请调用其 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法。 **SubmitMessage** 将邮件发送到传出队列中，并设置邮件的 MSGFLAG_SUBMIT PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 标记。 
  
如果邮件存储提供程序与传输提供程序紧密耦合，则直接将邮件发送到传输，传输传输将邮件发送到邮件系统。 如果未紧密耦合，邮件存储提供程序将通知 MAPI 后台处理程序传出队列已更改，并且 MAPI 后台处理程序将邮件传输给相应的传输提供程序。
  
如果允许用户取消发送操作，请调用 [IMsgStore：：AbortSubmit](imsgstore-abortsubmit.md) 来实现此功能。 **AbortSubmit** 将邮件从传出队列中删除。 允许用户阻止发送，直到邮件发送给基础邮件系统。 
  
如果 **SubmitMessage** 返回 MAPI_E_CORRUPT_DATA，则假定正在发送的数据现已丢失。 在尝试发送第二次之前，请通过调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 和 [IMAPIProp：：SaveChanges 重新编写邮件](imapiprop-savechanges.md)。 如果这些 **IMAPIProp** 调用失败或 **SubmitMessage** 再次失败，则向用户显示错误。 
  
成功调用 **SubmitMessage** 后，释放为收件人列表分配的任何内存，并释放邮件及其附件。 一旦发送消息，MAPI 将不允许对这些对象的指针执行任何其他操作。 一个例外是调用 **IUnknown：：Release**。 不允许其他调用，因为许多邮件存储提供程序使已发送的邮件的条目标识符无效。
  

