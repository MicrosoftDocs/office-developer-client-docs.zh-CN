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
  
传输提供程序动态链接库 (DLL) 提供了 MAPI 后台处理程序与负责邮件发送和接收的邮件系统部分之间的接口。 MAPI 后台处理程序和传输提供程序协同工作以处理发送邮件或接收邮件的责任。 MAPI 后台处理程序在首次使用传输提供程序 DLL 时加载该 DLL，并释放它（当不再需要它时）。 可以在同一系统中安装多个传输提供程序，但 MAPI 提供所需的一个后台处理程序。
  
客户端应用程序通常不直接与传输提供程序通信。 相反，客户端通过存储提供程序提交邮件，MAPI 后台处理程序将传出邮件发送到相应的传输提供程序，并将传入邮件发送到相应的邮件存储。 MAPI 后台处理程序执行其工作，在前台应用程序空闲时调用传输提供程序。 在首次登录传输提供程序时（可选）显示对话框后，除非客户端调用来刷新发送和接收队列，否则传输提供程序将在后台运行。 
  
传输提供程序在 MAPI 邮件系统中承担以下责任：
  
- 使用 MAPI 后台处理程序注册他们可以接受的地址类型，以便 MAPI 后台处理程序可以将邮件提交到相应的传输提供程序，具体取决于邮件的目标地址。 一个传输提供程序可以注册多个地址类型。 传输提供程序还可以在 MAPI 后台处理程序中注册特定收件人的地址。 发送到其中一个地址的邮件将提交到向 MAPI 后台处理程序注册地址的传输提供程序。 有关详细信息，请参阅传输 [提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 将传入邮件传递至 MAPI 后台处理程序。 根据邮件系统的性质，传输提供程序可以在新邮件到达时直接通知 MAPI 后台处理程序，也可以请求 MAPI 后台处理程序定期轮询传输提供程序以检查新邮件。
    
- 将 MAPI 邮件属性转换为邮件系统本机的邮件属性，以及从邮件属性转换邮件属性。 例如，传输提供程序可能必须将传出邮件中的发件人和收件人地址转换为邮件系统可接受的格式。 某些邮件系统不支持所有 MAPI 邮件属性。 有关在将邮件传递至邮件系统时保留 MAPI 邮件属性的信息，请参阅 Developing [a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md)。
    
- 注册特定于传输提供程序的邮件和收件人选项。
    
- 对邮件系统所需的凭据执行任何验证。
    
- 使用 MAPI 后台处理程序传递给它的 message 对象访问出站邮件。
    
- 根据基础邮件系统要求转换邮件格式。
    
- 通过为这些收件人设置 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性，通知 MAPI 后台处理程序传输提供程序已接受处理传出邮件的收件人。
    
- 需要处理传入邮件时通知 MAPI 后台处理程序。
    
- 使用 message 对象将传入邮件数据传递到 MAPI 后台处理程序。
    
- 将值分配给传入邮件上所有必需的 MAPI 邮件属性。
    
- 如有必要，在传递之后从基础邮件系统中删除邮件。
    
- 提供 MAPI 后台处理程序和客户端应用程序的状态信息。
    
下图显示了传输提供程序在 MAPI 体系结构的其他组件方面的角色。
  
**在消息系统传输提供程序角色**
  
![邮件系统中邮件系统传输](media/xp01.gif "提供程序角色中的传输提供程序角色")
  

