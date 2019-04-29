---
title: MAPI 主标识
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8787a873-6752-4b17-8ea3-8fed793e1371
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bf88de280b012c54d4caaac6bdfe877f476ac37
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404720"
---
# <a name="mapi-primary-identity"></a>MAPI 主标识

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
大多数 MAPI 会话都有特定的服务提供程序, 可提供会话的主要标识。 通常情况下, 它是通讯簿提供程序, 通过其邮件用户对象或通讯组列表之一提供标识。 事实上, MAPI 建议包含通讯簿提供程序的邮件服务对主要标识使用其对象之一。 当属于邮件服务的服务提供商提供主要标识时, 邮件服务中的所有其他服务提供程序都将共享此标识。
  
mapisvc.inf。INF 配置文件具有与邮件服务和服务提供程序级别的标识相关的条目。 邮件服务部分必须包括一个条目, 指明服务是否可以提供主标识;仅当提供程序可以提供标识时, 服务提供程序节才包含类似的条目。
  
下表列出了 mapisvc.inf 中的 "邮件服务" 和 "服务提供商" 部分中显示的条目。INF 文件。
  
|**主标识提供商**|**PR_RESOURCE_FLAGS 设置**|
|:-----|:-----|
|邮件服务  <br/> | `SERVICE_PRIMARY_IDENTITY` <br/> |
|不是邮件服务  <br/> | `SERVICE_NO_PRIMARY_IDENTITY` <br/> |
|服务提供程序  <br/> | `STATUS_PRIMARY_IDENTITY` <br/> |
   
尽管多个邮件服务可以声明其提供会话主要标识的能力, 但只选择一个邮件服务执行此操作。 此选择可能会发生:
  
- 创建配置文件时。
    
- 当客户端调用**IMsgServiceAdmin:: SetPrimaryIdentity**以显式方式将特定邮件服务设置为会话标识的提供程序。 了解详细信息。 请参阅[IMsgServiceAdmin:: SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。
    
创建配置文件时, MAPI 会指定要配置的第一条邮件服务, 其中包含在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置的 STATUS_PRIMARY_IDENTITY 标志的提供程序, 以提供主要标识. 在指定的邮件服务中, 选择使用此资源标志集配置的第一个提供程序以提供服务的标识。 对于在配置文件中指定的服务和其他邮件服务中的所有其他提供程序, 将清除 STATUS_PRIMARY_IDENTITY 标志。 如果从配置文件中删除提供程序提供主标识的任何时候, MAPI 都会为要配置的下一个提供程序分配可提供标识的角色。 这取决于 mapisvc.inf 的提供程序部分`PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY`中条目的外观。 
  
当客户端调用 message service 的**IMsgServiceAdmin:: SetPrimaryIdentity**方法时, 它将为目标服务中的服务提供程序指定 MAPIUID。 有关详细信息, 请参阅[MAPIUID](mapiuid.md)。 分配的服务提供程序由**MAPIUID**表示, 以提供邮件服务和会话的主要标识, 并且服务中的所有其他提供程序将共享此标识。 
  
负责提供主标识的消息服务中的每个提供程序都会更新其状态表中的行, 以包含以下属性。
  
|**主标识属性**|**设置为**|
|:-----|:-----|
|**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))  <br/> |提供主标识的对象的显示名称。  <br/> |
|**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))  <br/> |提供主标识的对象的搜索关键字。  <br/> |
|**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))  <br/> |提供主标识的对象的条目标识符。  <br/> |
   
 **检索提供主要标识的对象的条目标识符**
  
- 调用**IMAPISession:: QueryIdentity**方法。 有关详细信息, 请参阅[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)。 **QueryIdentity**在状态表中搜索包含值 STATUS_PRIMARY_IDENTITY 在其**PR_RESOURCE_FLAGS**列中的行, 并将相应的**PR_IDENTITY_ENTRYID**作为主实例的条目标识符返回窃取. 
    

