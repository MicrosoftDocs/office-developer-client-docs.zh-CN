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
  
大多数 MAPI 会话都有一个为会话提供主标识的特定服务提供程序。 通常，它是通讯簿提供程序，通过邮件传递用户对象或通讯组列表之一提供标识。 事实上，MAPI 建议包含通讯簿提供程序的邮件服务使用其对象之一作为主标识。 当属于邮件服务的服务提供商提供主标识时，邮件服务中的所有其他服务提供商将共享此标识。
  
MAPISVC。INF 配置文件在邮件服务和服务提供商级别都有与标识相关的条目。 邮件服务部分必须包含一个条目，该条目指出服务是否可以提供主标识;只有在提供程序提供标识时，服务提供程序部分才包括类似的条目。
  
下表列出了 MAPISVC 中邮件服务和服务提供程序部分出现的条目。INF 文件。
  
|**主要标识供应商**|**PR_RESOURCE_FLAGS设置**|
|:-----|:-----|
|邮件服务  <br/> | `SERVICE_PRIMARY_IDENTITY` <br/> |
|不是邮件服务  <br/> | `SERVICE_NO_PRIMARY_IDENTITY` <br/> |
|服务提供程序  <br/> | `STATUS_PRIMARY_IDENTITY` <br/> |
   
尽管多个邮件服务可以声明它们提供会话的主标识的能力，但仅选择了一个邮件服务来这样做。 此选择可能发生：
  
- 创建配置文件时。
    
- 当客户端调用 **IMsgServiceAdmin：：SetPrimaryIdentity** 以明确建立特定邮件服务作为会话标识的提供程序时。 有关详细信息。 请参阅 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。
    
创建配置文件时，MAPI 指定要配置的第一个邮件服务，其中包括在其 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 **STATUS_PRIMARY_IDENTITY** 标志的提供程序，以提供主标识。 在指定的邮件服务中，将选择第一个要配置此资源标志集的提供程序，以提供该服务的标识。 为STATUS_PRIMARY_IDENTITY服务中的所有其他提供程序和配置文件中的其他邮件服务清除此标记。 如果随时从配置文件中删除提供主标识的提供程序，MAPI 将角色分配给下一个可以提供标识的提供程序。 这由  `PR_RESOURCE_FLAGS=STATUS_PRIMARY_IDENTITY` MAPISVC.INF 中提供程序部分中条目的外观决定。 
  
当客户端调用邮件服务的 **IMsgServiceAdmin：：SetPrimaryIdentity** 方法时，它会为目标服务中的服务提供商指定 MAPIUID。 有关详细信息，请参阅 [MAPIUID](mapiuid.md)。 **MAPIUID** 表示的服务提供商被分配为提供邮件服务和会话的主标识，服务中的所有其他提供程序将共享此标识。 
  
邮件服务中负责提供主标识的每一个提供程序都会更新其状态表中的行，以包括以下属性。
  
|**主标识属性**|**设置为**|
|:-----|:-----|
|**PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))   <br/> |提供主标识的对象的显示名称。  <br/> |
|**PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))   <br/> |提供主标识的对象的搜索键。  <br/> |
|**PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md)  <br/> |提供主标识的对象的条目标识符。  <br/> |
   
 **检索提供主标识的对象的条目标识符**
  
- 调用 **IMAPISession：：QueryIdentity** 方法。 有关详细信息，请参阅 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md)。 **QueryIdentity** 在状态表中搜索在其 PR_RESOURCE_FLAGS 列中包含 **值 STATUS_PRIMARY_IDENTITY** 的行，并返回相应的 **PR_IDENTITY_ENTRYID** 作为主标识的条目标识符。 
    

