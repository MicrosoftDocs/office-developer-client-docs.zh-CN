---
title: 在邮件服务中添加或删除提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44bb4d34-ca96-4d5a-93fe-85e09bd7971d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 05d6d548032476062127f21b23aa2ce141ed1b65
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774512"
---
# <a name="adding-or-deleting-providers-in-a-message-service"></a>在邮件服务中添加或删除提供程序

  
  
**适用于**： Outlook 
  
若要添加或删除的消息服务服务提供商，请使用[IProviderAdmin: IUnknown](iprovideradminiunknown.md)接口。 您可以通过调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)检索**IProviderAdmin**指针。 提供程序表中，通过[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)，读取列出了有关当前安装的消息服务中的服务提供程序的信息。 客户端和服务提供商可以使用提供程序表中访问的提供程序 DLL 文件，例如，或**MAPIUID**、 显示名称和提供程序以及有关消息服务的信息的类型名称。 有关详细信息，请参阅[提供程序表](provider-tables.md)。
  
 **若要添加或删除邮件服务中的服务提供商**
  
1. 调用**AdminServices**方法来访问邮件服务管理对象。 
    
2. 调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)访问邮件服务表。 
    
3. 构建使用和消息服务的名称匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) [SPropertyRestriction](spropertyrestriction.md)结构在属性限制修改。 
    
4. 调用邮件服务表[IMAPITable::FindRow](imapitable-findrow.md)方法，以表示目标的邮件服务表中找到的行。 
    
5. 调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)检索**IProviderAdmin**指针。 将**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列作为_lpUID_参数传递从消息服务表格行。 
    
6. 调用[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)访问提供程序表中。 
    
7. 构建使用匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) SPropertyRestriction 结构和服务提供程序的名称在属性限制添加或删除。 
    
8. 调用提供程序表中的[IMAPITable::FindRow](imapitable-findrow.md)方法，以代表目标的服务提供程序表中找到的行。 
    
9. 呼叫[IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md)添加提供程序或[IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md)移除邮件服务。 为**CreateProvider**，作为_lpszProvider_参数中传递提供程序的**PR_DISPLAY_NAME**属性。 哪种方法，通过作为_lpUID_参数提供程序的**PR_SERVICE_UID**属性。 已添加或删除的服务提供程序后，更改将不明显，直到创建一个新会话。 
    
另一种方法向一个配置文件服务提供商，专门消息存储提供程序，包括为提供程序构建的项标识符。 由于构建条目标识符要求的其格式的知识，此方法仅用于如果服务提供商已公开其条目标识符格式。 
  
具有新构造的条目标识符，客户端可以调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)。 MAPI 自动为服务提供商，创建配置文件中的配置文件一节，但不会将其添加到邮件服务。 
  
某些消息服务不允许动态修改; 此类型支持的是最多邮件服务。 另一种可能也可能不受支持的功能是能够直接访问消息服务的专用配置文件部分。 如果您使用的消息服务允许此类访问权限，它将发布**GUID**值，该值代表 MAPISVC.INF 中的专用一节。 可以将此**GUID**传递到[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)呼叫中以访问配置文件部分中。 
  

