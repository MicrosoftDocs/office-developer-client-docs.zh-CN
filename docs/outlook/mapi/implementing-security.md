---
title: 实现安全性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62db34a0-887c-4607-94ad-d8cae68b35c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f09d96fd8b35df6cafa81b3830642cf6d67806e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775822"
---
# <a name="implementing-security"></a>实现安全性

  
  
**适用于**： Outlook 
  
如果消息的系统要求，传输提供程序负责为实现适当的访问邮件系统的安全级别。 通过传输提供程序通过 MAPI 后台处理程序发送的每个传入或传出邮件处理提供程序的登录会话的上下文中。 传输提供程序可以向建立此类连接前提示用户的凭据的用户显示的登录对话框。 此外，传输提供程序可以存储安全属性范围内配置文件一节中的用户的以前输入的凭据，并使用它们的访问而不提示。
  
实现传输提供程序的安全时, 考虑以下事项：
  
- 与多个安装的服务提供程序，可以有大量的用户名和密码与用户关联。
    
- MAPI 允许与多个身份的多个会话。 提供程序鼓励支持多个会话，但不是需要这样做。
    
- 与用户的配置文件中的离散节，每个会话与传输提供程序相关联 MAPI。 传输提供程序可以使用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法可访问此部分中，可用于存储与此会话，包括凭据关联的任何信息。 
    
- 与多个已安装的传输提供程序，就不一定是 true 用户仅有单个电子邮件地址。 用户可以为每个已安装的传输提供程序具有单独的电子邮件地址，或为每个会话在单个提供程序可以具有不同的地址。
    
有关将凭据存储在配置文件部分的详细信息，请参阅[消息服务和配置文件](message-services-and-profiles.md)和[IProfSect: IMAPIProp](iprofsectimapiprop.md)。
  

