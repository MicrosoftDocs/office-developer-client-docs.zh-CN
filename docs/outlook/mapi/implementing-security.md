---
title: 实现安全性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62db34a0-887c-4607-94ad-d8cae68b35c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c430160ee508a86f36d840c7916c0516cfc10fbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417285"
---
# <a name="implementing-security"></a>实现安全性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件系统需要它，则传输提供程序负责实现适当的安全级别，以访问邮件系统。 MAPI 后台处理程序通过传输提供程序发送的每个传入或传出邮件在提供程序登录会话上下文中进行处理。 传输提供程序可以向用户显示登录对话框，该对话框在建立此类连接之前提示输入用户凭据。 或者，传输提供程序可以将用户以前输入的凭据存储在配置文件节内的安全属性范围内，并使用它们进行访问，而不提示。
  
实现传输提供程序的安全性时，请考虑以下事项：
  
- 通过多个已安装的服务提供商，可能会有很多与用户关联的名称和密码。
    
- MAPI 允许多个具有多个标识的会话。 建议提供程序支持多个会话，但不需要这样做。
    
- 与传输提供程序的每个会话都由 MAPI 与用户配置文件中的离散部分关联。 传输提供程序可以使用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法来访问此部分，可用于存储与此会话关联的任何信息，包括凭据。 
    
- 对于多个已安装的传输提供程序，用户只有一个电子邮件地址并不一定如此。 用户可以具有每个已安装的传输提供程序的单独电子邮件地址，也可以为单个提供程序上的每个会话提供不同的地址。
    
有关在配置文件部分存储凭据的信息， [请参阅邮件服务和](message-services-and-profiles.md) 配置文件和 [IProfSect ： IMAPIProp](iprofsectimapiprop.md)。
  

