---
title: 检索主要标识和提供程序标识
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d81bb81d-1708-4a8d-a4d5-c3ba087db9b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2a87e32fe21aa6fb1d9296c568a74da994c146bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778635"
---
# <a name="retrieving-primary-and-provider-identity"></a>检索主要标识和提供程序标识

  
  
**适用于**： Outlook 
  
服务提供商，通常通讯簿提供程序，必须提供标识的可以用来代表会话中很多情况下的选项。 三个属性说明提供程序的标识：
  
- **PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 
    
- **PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 
    
- **PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 
    
这些属性设置为条目标识符、 显示名称和相应的标识对象，它通常是邮件用户的搜索键。 提供标识提供程序还会在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_PRIMARY_IDENTITY 标志。
  
根据您的需要，可能会话使用特定提供程序的标识或主标识。 此外显示为了或检索属性，如**PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md))，您可以使用提供程序的标识。 **PR_RESOURCE_PATH**，如果设置，包含使用或提供程序创建的文件的路径。 检索**PR_RESOURCE_PATH**属性时要查找文件相关的会话的用户提供的主要标识提供程序。 
  
 **若要检索特定提供程序的标识**
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。 
    
2. 构建使用[SPropertyRestriction](spropertyrestriction.md)结构以匹配具有指定的提供程序的名称的**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 列限制。 
    
3. 调用[IMAPITable::FindRow](imapitable-findrow.md)以找到提供程序的行。 将在**PR_IDENTITY_ENTRYID**列中，存储提供程序的标识，如果存在。 
    
 **若要检索主标识会话**
  
- 调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)。 **QueryIdentity**基于状态表中的行之一**PR_RESOURCE_FLAGS**列中的 STATUS_PRIMARY_IDENTITY 值存在的会话标识。 如果没有的状态行设置此值， **QueryIdentity**会将标识分配给设置三个 PR_IDENTITY 属性的第一个服务提供程序。 如果没有服务提供商提供标识， **QueryIdentity**返回 MAPI_W_NO_SERVICE。 这种情况下，您应创建一个字符串，表示可以充当主标识一般用户。 
    
 **会话中明确地设置主标识**
  
- 调用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。 将**MAPIUID**传递的目标服务提供程序。 
    

