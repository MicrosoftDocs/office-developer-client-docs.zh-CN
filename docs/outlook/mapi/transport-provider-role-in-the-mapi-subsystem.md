---
title: MAPI 子系统中的传输提供程序角色
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7659369a-0952-4f5a-a86b-91958c4c1a3f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7ea60b73fb1abe32b6db5e3c73d6ef3fac53d35d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779000"
---
# <a name="transport-provider-role-in-the-mapi-subsystem"></a>MAPI 子系统中的传输提供程序角色
  
**适用于**： Outlook 
  
传输提供程序动态链接库 (Dll) 提供了 MAPI 后台处理程序和负责邮件发送和接收的邮件系统的一部分之间的接口。 MAPI 后台处理程序和传输提供程序一起工作以处理发送邮件还是接收邮件的职责。 MAPI 后台处理程序在首次使用并将其发布当不再需要时对其时加载传输提供程序 DLL。 多个传输提供程序可以安装在相同的系统，但 MAPI 提供所需一个后台处理程序。
  
客户端应用程序通常不能直接与传输提供程序。 相反，客户端将通过存储提供程序的邮件提交和 MAPI 后台处理程序将传出邮件发送到适当的传输提供程序，并将传入消息传送到相应的消息存储。 MAPI 后台处理程序自己的工作，并使其传输提供程序，当前景色的应用程序处于空闲状态的呼叫。 （可选） 在第一个传输提供程序时显示对话框登录后，传输提供程序在后台运行，除非由客户端刷新发送和接收队列中调用。 
  
传输提供程序的 MAPI 邮件系统中有以下责任：
  
- 参与者可以接受的地址类型注册 MAPI 后台处理程序，以便 MAPI 后台处理程序可以将邮件提交到适当的传输提供程序根据邮件的目标地址。 一个传输提供程序可以注册多个地址类型。 传输提供程序还可以使用 MAPI 后台处理程序注册特定收件人的地址。 邮件发送到这些地址之一将提交到传输提供程序注册 MAPI 后台处理程序的地址。 有关详细信息，请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 将传入邮件传递到 MAPI 后台处理程序。 根据邮件系统的性质，传输提供程序可以也直接通知 MAPI 后台处理程序时收到新邮件，或它可以请求 MAPI 后台处理程序轮询定期要检查新邮件的传输提供程序。
    
- 将邮件系统的本机的邮件属性与 MAPI 邮件属性相互转换。 例如，传输提供程序可能需要转换为邮件系统可接受的窗体中的传出邮件的发件人和收件人的地址。 某些消息系统不支持的所有 MAPI 邮件属性。 有关时邮件传递到邮件系统保留 MAPI 邮件属性的详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。
    
- 注册到传输提供程序特定的邮件和收件人选项。
    
- 执行任何的所需的邮件系统的凭据进行验证。
    
- 使用 message 对象的访问出站邮件传递给它的 MAPI 后台处理程序。
    
- 翻译所需的基础邮件系统的邮件格式。
    
- 通知 MAPI 后台处理程序的传输提供程序已接受负责处理通过**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为这些收件人的传出邮件的收件人。
    
- 当需要处理传入消息通知 MAPI 后台处理程序。
    
- 通过使用消息对象，将传入消息数据传递到 MAPI 后台处理程序。
    
- 将值分配给所有必需的 MAPI 邮件属性对传入邮件。
    
- 邮件从系统中删除基础消息后传递，如有必要。
    
- 提供 MAPI 后台处理程序和客户端应用程序的状态的信息。
    
下图显示与 MAPI 体系结构的其他组件的传输提供程序的角色。
  
**在消息系统传输提供程序角色**
  
![在消息系统传输提供程序角色](media/xp01.gif "在消息系统传输提供程序角色")
  

