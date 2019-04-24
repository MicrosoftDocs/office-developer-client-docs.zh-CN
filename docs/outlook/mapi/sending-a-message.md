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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339744"
---
# <a name="sending-a-message"></a>发送信息

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当您准备好发送邮件时, 请调用其[IMessage:: SubmitMessage](imessage-submitmessage.md)方法。 **SubmitMessage**将邮件放入传出队列, 并在邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_SUBMIT 标志。
  
邮件存储提供程序 (如果与传输提供程序紧密结合) 将直接向传输提供邮件, 并将邮件传递到邮件系统。 如果未紧密结合, 邮件存储提供程序将通知 mapi 后台处理程序传出队列已更改, mapi 后台处理程序将邮件传输到适当的传输提供程序。
  
如果允许用户取消发送操作, 请调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)以实现此功能。 **AbortSubmit**从传出队列中删除邮件。 在向基础邮件系统提供邮件之前, 可以允许用户停止发送。 
  
如果**SubmitMessage**返回 MAPI_E_CORRUPT_DATA, 则假定正在发送的数据现在已丢失。 在尝试发送第二次之前, 请通过调用[IMAPIProp:: SetProps](imapiprop-setprops.md)和[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)来重新编写邮件。 如果这些**IMAPIProp**调用失败, 或者**SubmitMessage**第二次失败, 则向用户显示一个错误。 
  
成功调用**SubmitMessage**后, 释放为收件人列表分配的所有内存并释放邮件及其附件。 一旦发送了邮件, MAPI 就不允许对这些对象的指针进行任何进一步的操作。 一个例外是调用**IUnknown:: Release**。 由于许多邮件存储提供程序对已发送邮件的条目标识符无效, 因此不允许任何其他呼叫。
  

