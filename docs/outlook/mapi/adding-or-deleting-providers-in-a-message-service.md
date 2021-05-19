---
title: 在邮件服务中添加或删除提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44bb4d34-ca96-4d5a-93fe-85e09bd7971d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ed5ea8bdfcbdaaa6b6abd81a39f0e8df50d3b314
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433421"
---
# <a name="adding-or-deleting-providers-in-a-message-service"></a>在邮件服务中添加或删除提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要在邮件服务中添加或删除服务提供程序，请使用 [IProviderAdmin ： IUnknown](iprovideradminiunknown.md) 接口。 可以通过调用 [IMsgServiceAdmin：：AdminProviders](imsgserviceadmin-adminproviders.md)来检索 **IProviderAdmin** 指针。 提供程序表（可以通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md)访问）列出了有关邮件服务中当前安装的服务提供商的信息。 客户端和服务提供程序可以使用提供程序表访问提供程序 DLL 文件的名称，例如 **，或者 MAPIUID**、显示名称 和提供程序的类型，以及有关邮件服务的信息。 有关详细信息，请参阅提供程序 [表](provider-tables.md)。
  
 **在邮件服务中添加或删除服务提供程序**
  
1. 调用 **AdminServices** 方法来访问邮件服务管理对象。 
    
2. 调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 以访问邮件服务表。 
    
3. 使用与要修改的邮件服务名称相匹配的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 的 [SPropertyRestriction](spropertyrestriction.md)结构构建属性限制。 
    
4. 调用邮件服务表的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法来查找表中表示目标邮件服务的行。 
    
5. 调用 [IMsgServiceAdmin：：AdminProviders](imsgserviceadmin-adminproviders.md) 以检索 **IProviderAdmin** 指针。 将邮件 **PR_SERVICE_UID (** [PidTagServiceUid) 行中的 PidTagServiceUid](pidtagserviceuid-canonical-property.md) 参数作为  _lpUID_ 参数传递。 
    
6. 调用 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md) 以访问提供程序表。 
    
7. 使用与要添加或删除的服务提供商的名称匹配的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 的 SPropertyRestriction 结构构建属性限制。 
    
8. 调用提供程序表的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法来查找表中表示目标服务提供商的行。 
    
9. 调用 [IProviderAdmin：：CreateProvider](iprovideradmin-createprovider.md) 以添加提供程序或 [IProviderAdmin：:D eleteProvider](iprovideradmin-deleteprovider.md) 以将其从邮件服务中删除。 对于 **CreateProvider**，将提供程序的 **PR_DISPLAY_NAME** 属性作为  _lpszProvider_ 参数传递。 对于任一方法，将提供程序的 **PR_SERVICE_UID** 属性作为  _lpUID_ 参数传递。 添加或删除服务提供商后，在新建会话之前，更改不会显现出来。 
    
向配置文件中添加服务提供程序（特别是邮件存储提供程序）的另一种技术涉及构造提供程序的条目标识符。 由于构造条目标识符需要了解其格式，因此只有在服务提供商公开其条目标识符格式时，才能使用这种技术。 
  
使用新构造的条目标识符，客户端可以调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)。 MAPI 会自动在服务提供程序的配置文件中创建配置文件节，但不将其添加到邮件服务。 
  
某些邮件服务不允许这种类型的动态修改;是否受支持取决于邮件服务。 另一个可能受支持也可能不受支持的功能是直接访问邮件服务的专用配置文件部分的功能。 如果您使用的邮件服务允许此类访问，它将发布表示 MAPISVC.INF 中的专用节的 **GUID。** 您可以在对 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md)的调用中传递此 **GUID** 以访问配置文件部分。 
  

