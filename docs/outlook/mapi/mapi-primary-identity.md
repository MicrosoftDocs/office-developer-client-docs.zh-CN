---
title: MAPI 主标识
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8787a873-6752-4b17-8ea3-8fed793e1371
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bd6fe1298a38733cb9d4916a931138c616e110bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776285"
---
# <a name="mapi-primary-identity"></a>MAPI 主标识

  
  
**适用于**： Outlook 
  
大多数 MAPI 会话具有会话中提供的主要标识的特定服务提供商。 通常，它是通讯簿提供程序，它提供标识通过其消息的用户对象或通讯组列表之一。 实际上，MAPI 建议消息服务包括通讯簿提供程序的主标识使用它的一个对象。 当所属的消息服务的服务提供商提供的主要标识时，消息服务中其他服务提供商的所有共享此标识。
  
MAPISVC。INF 配置文件具有与 identity 同时在消息服务和服务提供程序级别的条目。 消息服务部分必须包括一个条目，指出该服务可以提供的主要标识;服务提供程序部分仅时的提供程序可以提供标识包含类似的项。
  
下表列出了消息服务和 MAPISVC 中的服务提供程序部分中显示的项。INF 文件。
  
|**主标识供应商**|**PR_RESOURCE_FLAGS 设置**|
|:-----|:-----|
|邮件服务  <br/> | `SERVICE_PRIMARY_IDENTITY` <br/> |
|不邮件服务  <br/> | `SERVICE_NO_PRIMARY_IDENTITY` <br/> |
|服务提供商  <br/> | `STATUS_PRIMARY_IDENTITY` <br/> |
   
虽然多个邮件服务可以将其能够提供会话的主标识声明，只有一个邮件服务处于选中状态，这样做。 可能会出现此选项：
  
- 创建一个配置文件时。
    
- 当客户端调用**IMsgServiceAdmin::SetPrimaryIdentity**以显式建立的会话标识提供程序的特定消息服务。 有关详细信息。 请参阅[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。
    
MAPI 配置文件创建时，指定第一个邮件服务配置包含用 STATUS_PRIMARY_IDENTITY 标志设置其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中提供的主要标识提供程序. 中指定的邮件服务，要配置设置此资源标志的第一个提供程序选择提供服务的标识。 对指定的服务和配置文件中的其他消息服务中的所有其他提供程序清除 STATUS_PRIMARY_IDENTITY 标志。 如果在任何时候提供主要身份提供程序已从配置文件，MAPI 分配到要配置的下一个提供程序可以提供标识的角色。 这由的外观`PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY`中 MAPISVC.INF 的提供程序的一节中的条目。 
  
当客户端呼叫消息服务的**IMsgServiceAdmin::SetPrimaryIdentity**方法时，它指定 MAPIUID 中目标服务的服务提供商。 有关详细信息，请参阅[MAPIUID](mapiuid.md)。 分配由**MAPIUID**服务提供商提供的主要标识邮件服务和会话，且所有服务中的其他提供程序将共享此标识。 
  
负责提供的主要标识的消息服务中的每个提供程序更新其状态表，包括以下属性中的行。
  
|**主要的 identity 属性**|**设置为**|
|:-----|:-----|
|**PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))  <br/> |提供的主要标识对象的显示名称。  <br/> |
|**PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))  <br/> |搜索对象提供的主要标识键。  <br/> |
|**PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))  <br/> |提供的主要标识的对象的项标识符。  <br/> |
   
 **若要检索的对象提供的主要标识的条目标识符**
  
- 调用**IMAPISession::QueryIdentity**方法。 有关详细信息，请参阅[IMAPISession::QueryIdentity](imapisession-queryidentity.md)。 **QueryIdentity**搜索状态表，包含其**PR_RESOURCE_FLAGS**列中的值 STATUS_PRIMARY_IDENTITY 并返回相应**PR_IDENTITY_ENTRYID**作为主的项标识符的行标识。 
    

