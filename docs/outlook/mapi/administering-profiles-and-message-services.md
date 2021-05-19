---
title: 管理配置文件和邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89a2ac43-9601-47fc-b736-db48585fe879
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e64241008a4adde4431b2c9683199294f21e396
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410558"
---
# <a name="administering-profiles-and-message-services"></a>管理配置文件和邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件和邮件服务管理可涉及创建新配置文件、删除旧配置文件，以及通过更改现有配置文件中包含的邮件服务和服务提供程序来修改现有配置文件的内容。 并非所有客户端都支持将配置文件和邮件服务管理作为标准功能。 有些客户端与配置文件只与允许用户在登录时选择一个配置文件有关。
  
如果支持配置文件或邮件服务管理，则有可能使用以下 MAPI 实现的接口：
  
- [IMsgServiceAdmin ：IUnknown](imsgserviceadminiunknown.md) 用于管理配置文件中的消息服务，可通过 [IMAPISession：：AdminServices](imapisession-adminservices.md) 或 [IProfAdmin：：AdminServices 访问](iprofadmin-adminservices.md)。 消息客户端通常调用 **IMAPISession，** 而配置客户端或不发送或接收消息的客户端调用 **IProfAdmin**。 尽可能调用 **IProfAdmin** 方法，因为它不会导致邮件服务启动。 有关使用 **IMsgServiceAdmin** 接口的详细信息，请参阅下列主题 [：Configuring a Message Service、Copying](configuring-a-message-service.md)a Message [Service](copying-a-message-service.md)和 [Deleting a Message Service。](deleting-a-message-service.md)
    
- [IProfAdmin ：IUnknown](iprofadminiunknown.md) 用于管理可通过 [MAPIAdminProfiles](mapiadminprofiles.md) 函数访问的配置文件。 有关使用 **IProfAdmin** 接口的信息，请参阅下列主题：使用自定义 [](creating-a-profile-by-using-custom-code.md)代码创建配置文件、复制配置文件、删除配置文件、查找配置文件 [](deleting-a-profile.md)名称以及设置默认 [配置文件](setting-a-default-profile.md)。 [](copying-a-profile.md) [](finding-a-profile-name.md)
    
- [IProfSect ：IMAPIProp，](iprofsectimapiprop.md) 用于维护配置文件节中的属性，可通过 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md) 或 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md) 方法访问。 有关配置文件部分详细信息，请参阅 [MAPI Profiles](mapi-profiles.md)。
    
- [IProviderAdmin ： IUnknown](iprovideradminiunknown.md) 用于管理邮件服务中的服务提供程序，可通过 [IMsgServiceAdmin：：AdminProviders 访问](imsgserviceadmin-adminproviders.md)。 有关使用 **IProviderAdmin** 接口的信息，请参阅 [Adsing or Deleting Providers in a Message Service。](adding-or-deleting-providers-in-a-message-service.md)
    
请谨慎支持配置文件和邮件服务管理。 没有防止对使用中的配置文件进行不良修改的安全措施。 MAPI 可以阻止您删除使用中的配置文件，但无法阻止您删除它内每个邮件服务。 如果删除配置文件中的每个邮件服务，则这些服务的所有服务提供程序将停止，从而导致出现不可预知的结果。
  
## <a name="in-this-section"></a>本节内容

[创建配置文件](creating-a-profile.md)
  
> 介绍如何创建配置文件。
    
[复制配置文件](copying-a-profile.md)
  
> 介绍如何复制配置文件。
    
[删除配置文件](deleting-a-profile.md)
  
> 介绍如何删除配置文件。
    
[设置默认配置文件](setting-a-default-profile.md)
  
> 介绍如何设置默认配置文件。
    
[查找配置文件名称](finding-a-profile-name.md)
  
> 介绍如何查找配置文件的名称。
    
[添加邮件服务](adding-a-message-service.md)
  
> 介绍如何添加邮件服务。
    
[配置邮件服务](configuring-a-message-service.md)
  
> 介绍如何配置邮件服务。
    
[复制邮件服务](copying-a-message-service.md)
  
> 介绍如何将邮件服务复制到配置文件。
    
[删除邮件服务](deleting-a-message-service.md)
  
> 介绍如何删除邮件服务。
    
[在邮件服务中添加或删除提供程序](adding-or-deleting-providers-in-a-message-service.md)
  
> 介绍如何在邮件服务中添加或删除提供程序。
    

