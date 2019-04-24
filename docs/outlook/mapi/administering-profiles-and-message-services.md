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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330231"
---
# <a name="administering-profiles-and-message-services"></a>管理配置文件和邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件和邮件服务管理可以通过更改包含在现有配置文件中的邮件服务和服务提供程序来创建新的配置文件、删除旧的配置文件以及修改现有配置文件的内容。 并非所有客户端都支持作为标准功能的配置文件和邮件服务管理。 有些客户端与配置文件无关, 而不是允许其用户在登录时选择一个。
  
如果您支持配置文件或邮件服务管理, 则可能会使用 MAPI 实现的以下接口:
  
- [IMsgServiceAdmin:](imsgserviceadminiunknown.md)用于管理配置文件中的邮件服务的 IUnknown, 可通过[IMAPISession:: AdminServices](imapisession-adminservices.md)或[IProfAdmin:: AdminServices](iprofadmin-adminservices.md)访问。 邮件客户端通常会在配置客户端或不发送或接收邮件的客户端调用**IMAPISession**时调用**IProfAdmin**。 只要有可能, 请调用**IProfAdmin**方法, 因为它不会导致启动邮件服务。 有关使用**IMsgServiceAdmin**接口的详细信息, 请参阅下列主题:[配置邮件服务](configuring-a-message-service.md)、[复制邮件服务](copying-a-message-service.md)和[删除邮件服务](deleting-a-message-service.md)。
    
- [IProfAdmin:](iprofadminiunknown.md)用于管理配置文件的 IUnknown, 可通过[MAPIAdminProfiles](mapiadminprofiles.md)函数访问。 有关使用**IProfAdmin**接口的详细信息, 请参阅下列主题:[使用自定义代码创建配置](creating-a-profile-by-using-custom-code.md)文件、[复制配置文件](copying-a-profile.md)、[删除配置文件](deleting-a-profile.md)、[查找配置文件名称](finding-a-profile-name.md)和[设置默认配置文件](setting-a-default-profile.md)。
    
- [IProfSect: IMAPIProp](iprofsectimapiprop.md)若要维护配置文件节中的属性, 可通过[IMAPISession:: OpenProfileSection](imapisession-openprofilesection.md)或[IProviderAdmin:: OpenProfileSection](iprovideradmin-openprofilesection.md)方法访问。 有关配置文件节的详细信息, 请参阅[MAPI 配置文件](mapi-profiles.md)。
    
- [IProviderAdmin:](iprovideradminiunknown.md)用于管理邮件服务中的服务提供程序的 IUnknown, 可通过[IMsgServiceAdmin:: AdminProviders](imsgserviceadmin-adminproviders.md)访问。 有关使用**IProviderAdmin**接口的详细信息, 请参阅[在邮件服务中添加或删除提供程序](adding-or-deleting-providers-in-a-message-service.md)。
    
对配置文件和邮件服务管理的支持时要小心。 没有可防止对正在使用的配置文件进行负面修改的安全措施。 MAPI 可以阻止您删除正在使用的配置文件, 但不能阻止您删除其中的每个邮件服务。 如果您删除配置文件中的每个邮件服务, 这些服务中的所有服务提供程序都将停止, 从而导致出现不可预知的结果。
  
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
    

