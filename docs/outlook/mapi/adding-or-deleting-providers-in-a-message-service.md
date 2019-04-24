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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329559"
---
# <a name="adding-or-deleting-providers-in-a-message-service"></a>在邮件服务中添加或删除提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要在邮件服务中添加或删除服务提供程序, 请使用[IProviderAdmin: IUnknown](iprovideradminiunknown.md)接口。 您可以通过调用[IMsgServiceAdmin:: AdminProviders](imsgserviceadmin-adminproviders.md)检索**IProviderAdmin**指针。 提供程序表通过[IProviderAdmin:: GetProviderTable](iprovideradmin-getprovidertable.md)进行访问时, 列出了有关当前安装在邮件服务中的服务提供程序的信息。 客户端和服务提供程序可以使用提供程序表访问提供程序 DLL 文件的名称, 例如, 或者提供程序的**MAPIUID**、显示名称和类型, 以及有关邮件服务的信息。 有关详细信息, 请参阅[Provider Tables](provider-tables.md)。
  
 **在邮件服务中添加或删除服务提供程序**
  
1. 调用**AdminServices**方法以访问邮件服务管理对象。 
    
2. 调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)以访问邮件服务表。 
    
3. 使用匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 的[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 将邮件服务的名称与要修饰. 
    
4. 调用邮件服务表的[IMAPITable:: FindRow](imapitable-findrow.md)方法以定位表示目标邮件服务的表中的行。 
    
5. 调用[IMsgServiceAdmin:: AdminProviders](imsgserviceadmin-adminproviders.md)以检索**IProviderAdmin**指针。 将邮件服务表行中的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列作为_lpUID_参数进行传递。 
    
6. 调用[IProviderAdmin:: GetProviderTable](iprovideradmin-getprovidertable.md)以访问提供程序表。 
    
7. 使用与要包含的服务提供程序的名称匹配的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 的 SPropertyRestriction 结构生成属性限制添加或删除。 
    
8. 调用提供程序表的[IMAPITable:: FindRow](imapitable-findrow.md)方法以定位表示目标服务提供程序的表中的行。 
    
9. 调用[IProviderAdmin:: CreateProvider](iprovideradmin-createprovider.md)以添加提供程序或[IProviderAdmin::D eleteprovider](iprovideradmin-deleteprovider.md)将其从邮件服务中删除。 对于**CreateProvider**, 将提供程序的**PR_DISPLAY_NAME**属性作为_lpszProvider_参数进行传递。 对于这两种方法, 请将提供程序的**PR_SERVICE_UID**属性作为_lpUID_参数进行传递。 在添加或删除服务提供程序后, 在创建新会话之前, 更改不会明显。 
    
将服务提供程序 (特别是邮件存储提供程序) 添加到配置文件中的另一种方法涉及到为提供程序构造条目标识符。 由于构造条目标识符需要了解其格式, 因此仅当服务提供程序已将其条目标识符格式设为 public 时, 才能使用此技术。 
  
使用新构造的条目标识符, 客户端可以调用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)。 MAPI 会在服务提供程序的配置文件中自动创建配置文件部分, 但不会将其添加到邮件服务中。 
  
某些邮件服务不允许此类型的动态修改;是否支持的是最新的邮件服务。 可能支持也可能不受支持的另一项功能是能够直接访问邮件服务的专用配置文件节。 如果您使用的邮件服务允许此类访问, 它将发布表示 mapisvc.inf 中的 private 部分的**GUID** 。 可以在对[IProviderAdmin:: OpenProfileSection](iprovideradmin-openprofilesection.md)的调用中传递此**GUID** , 以访问配置文件部分。 
  

