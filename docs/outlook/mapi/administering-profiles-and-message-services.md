---
title: 管理配置文件和邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89a2ac43-9601-47fc-b736-db48585fe879
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 71e8cf50c1951abf1df6163cae4757ffebc979b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774516"
---
# <a name="administering-profiles-and-message-services"></a>管理配置文件和邮件服务

  
  
**适用于**： Outlook 
  
配置文件和消息服务管理可涉及创建新配置文件，删除旧的配置文件，并通过更改消息服务和服务提供商，其中包含修改现有配置文件的内容。 并非所有客户端支持为标准版功能的配置文件和消息服务管理。 某些客户端有什么要使用配置文件不是允许用户可以选择其中一个在登录时执行的操作。
  
如果您支持配置文件或消息服务管理，很可能将使用的由 MAPI 实现以下接口：
  
- [IMsgServiceAdmin: IUnknown](imsgserviceadminiunknown.md)管理配置文件，可以通过[IMAPISession::AdminServices](imapisession-adminservices.md)或[IProfAdmin::AdminServices](iprofadmin-adminservices.md)访问中的消息服务。 通常，消息客户端配置客户端或不发送或接收邮件，呼叫**IProfAdmin**的客户端时调用**IMAPISession** 。 只要有可能，调用**IProfAdmin**方法，因为它不会导致邮件服务启动。 有关使用**IMsgServiceAdmin**接口的详细信息，请参阅下列主题：[消息服务配置](configuring-a-message-service.md)、[复制邮件服务](copying-a-message-service.md)和[删除邮件服务](deleting-a-message-service.md)。
    
- [IProfAdmin: IUnknown](iprofadminiunknown.md)管理配置文件，可通过[MAPIAdminProfiles](mapiadminprofiles.md)函数。 有关使用**IProfAdmin**接口的详细信息，请参阅下列主题：[创建一个配置文件使用自定义代码](creating-a-profile-by-using-custom-code.md)、[复制一个配置文件](copying-a-profile.md)，[删除配置文件](deleting-a-profile.md)、[查找配置文件的名称](finding-a-profile-name.md)和[设置默认配置文件](setting-a-default-profile.md)。
    
- [IProfSect: IMAPIProp](iprofsectimapiprop.md)维护配置文件内容，可通过[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)或[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)方法访问中的属性。 有关配置文件节的详细信息，请参阅[MAPI 配置文件](mapi-profiles.md)。
    
- [IProviderAdmin: IUnknown](iprovideradminiunknown.md)管理消息服务，可通过[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)访问中的服务提供程序。 有关使用**IProviderAdmin**接口的详细信息，请参阅[添加或删除邮件服务中的提供程序](adding-or-deleting-providers-in-a-message-service.md)。
    
注意在您的配置文件和消息服务管理的支持。 没有任何安全措施防御产生不利修改正在使用的配置文件。 MAPI 可以防止删除配置文件中使用，但无法防止删除在每个邮件服务。 如果您删除配置文件中的每个邮件服务，所有这些服务的服务提供程序将停止从而导致无法预料的结果发生。
  
## <a name="in-this-section"></a>本节内容

[创建配置文件](creating-a-profile.md)
  
> 介绍如何创建一个配置文件。
    
[复制配置文件](copying-a-profile.md)
  
> 介绍如何将配置文件复制。
    
[删除配置文件](deleting-a-profile.md)
  
> 介绍如何删除配置文件。
    
[设置默认配置文件](setting-a-default-profile.md)
  
> 介绍如何设置默认配置文件。
    
[查找配置文件名称](finding-a-profile-name.md)
  
> 介绍如何查找配置文件的名称。
    
[添加邮件服务](adding-a-message-service.md)
  
> 介绍如何添加邮件服务。
    
[配置邮件服务](configuring-a-message-service.md)
  
> 介绍如何配置的消息服务。
    
[复制邮件服务](copying-a-message-service.md)
  
> 介绍如何向一个配置文件复制的消息服务。
    
[删除邮件服务](deleting-a-message-service.md)
  
> 介绍如何删除消息服务。
    
[在邮件服务中添加或删除提供程序](adding-or-deleting-providers-in-a-message-service.md)
  
> 介绍如何添加或删除的消息服务提供程序。
    

