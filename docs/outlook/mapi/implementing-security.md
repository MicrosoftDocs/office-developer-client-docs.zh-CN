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
  
如果邮件系统需要它, 则传输提供程序负责实现相应的安全级别, 以访问邮件系统。 MAPI 后台处理程序通过传输提供程序发送的每封传入或传出邮件在提供程序登录会话的上下文中进行处理。 在建立此类连接之前, 传输提供程序可以向用户显示登录对话框, 以提示输入用户的凭据。 或者, 传输提供程序可以将用户以前输入的凭据存储在 profile 节内的安全属性范围中, 并将其用于 access, 而无需提示。
  
在实现传输提供程序的安全性时, 请考虑以下事项:
  
- 在安装了多个服务提供程序的情况下, 可能会有许多与用户相关联的名称和密码。
    
- MAPI 允许多个会话具有多个标识。 鼓励提供商支持多个会话, 但这不是必需的。
    
- 与传输提供程序的每个会话都与用户配置文件中的离散部分的 MAPI 关联。 传输提供程序可以使用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法获取对此部分的访问权限, 这可用于存储与此会话相关联的任何信息, 包括凭据。 
    
- 如果有多个已安装的传输提供程序, 则不一定是用户只能有一个电子邮件地址。 用户可以为每个已安装的传输提供程序提供单独的电子邮件地址, 也可以为单个提供程序上的每个会话提供不同的地址。
    
有关在 profile 节中存储凭据的详细信息, 请参阅[Message Services and](message-services-and-profiles.md) profile and [IProfSect: IMAPIProp](iprofsectimapiprop.md)。
  

