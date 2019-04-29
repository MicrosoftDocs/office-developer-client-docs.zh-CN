---
title: MAPI 子系统中的传输提供程序角色
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7659369a-0952-4f5a-a86b-91958c4c1a3f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7cadb57706e3feec7ed98dd5e4e8d75967036fef
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424054"
---
# <a name="transport-provider-role-in-the-mapi-subsystem"></a>MAPI 子系统中的传输提供程序角色
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序动态链接库 (dll) 提供 MAPI 后台处理程序与负责邮件发送和接收的邮件系统部分之间的接口。 MAPI 后台处理程序和传输提供程序共同处理发送邮件或接收邮件的责任。 MAPI 后台处理程序在首次使用时加载传输提供程序 DLL, 并在不再需要时将其释放。 可以在同一个系统上安装多个传输提供程序, 但 MAPI 会提供一个需要的后台处理程序。
  
客户端应用程序通常不直接与传输提供程序进行通信。 相反, 客户端通过存储提供程序提交邮件, 而 MAPI 后台处理程序将传出邮件发送到相应的传输提供程序, 并将传入邮件传递到相应的邮件存储。 MAPI 后台处理程序执行其工作, 并在前台应用程序空闲时对传输提供程序进行调用。 当传输提供程序首次登录时显示对话框时, 传输提供程序将在后台运行, 除非由客户端调用以刷新发送和接收队列。 
  
在 MAPI 邮件系统中, 传输提供程序具有以下职责:
  
- 注册他们可以使用 MAPI 后台处理程序接受的地址类型, 以便 MAPI 后台处理程序可以将邮件提交到相应的传输提供程序, 具体取决于邮件的目标地址。 一个传输提供程序可以注册多个地址类型。 传输提供程序还可以使用 MAPI 后台处理程序注册特定收件人的地址。 发送到这些地址之一的邮件将被提交到使用 MAPI 后台处理程序注册地址的传输提供程序。 有关详细信息, 请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 将传入邮件传递到 MAPI 后台处理程序。 根据邮件系统的性质, 传输提供程序可以在新邮件到达时直接通知 mapi 后台处理程序, 也可以请求 mapi 后台处理程序定期轮询传输提供程序, 以检查是否有新邮件。
    
- 将 MAPI 邮件属性从本机邮件属性转换为邮件系统。 例如, 传输提供程序可能必须将传出邮件中发件人和收件人的地址转换为邮件系统可接受的表单。 某些邮件系统不支持所有 MAPI 邮件属性。 有关在将邮件传递到邮件系统时保留 MAPI 邮件属性的详细信息, 请参阅[开发启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。
    
- 注册特定于传输提供程序的邮件和收件人选项。
    
- 对邮件系统所需的凭据执行任何验证。
    
- 使用 MAPI 后台处理程序传递给出站邮件的邮件对象访问出站邮件。
    
- 根据基础邮件系统的要求翻译邮件格式。
    
- 通知 MAPI 后台处理程序传出邮件的收件人: 传输提供程序已接受通过设置这些收件人的**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性来进行处理的责任。
    
- 需要处理传入邮件时通知 MAPI 后台处理程序。
    
- 使用 message 对象将传入邮件数据传递到 MAPI 后台处理程序。
    
- 将值分配给传入邮件的所有必需的 MAPI 邮件属性。
    
- 如果需要, 在传递后从基础邮件系统中删除邮件 (如有必要)。
    
- 提供 MAPI 后台处理程序和客户端应用程序的状态信息。
    
下图显示了与 MAPI 体系结构的其他组件相关的传输提供程序的角色。
  
**在消息系统传输提供程序角色**
  
![邮件系统中的传输提供程序角色](media/xp01.gif "邮件系统中的传输提供程序角色")
  

