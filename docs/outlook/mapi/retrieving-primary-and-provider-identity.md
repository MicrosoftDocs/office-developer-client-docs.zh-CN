---
title: 检索主标识和提供程序标识
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d81bb81d-1708-4a8d-a4d5-c3ba087db9b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f59695eca2af71dd592c5b3a755d021ac53b3e31
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430810"
---
# <a name="retrieving-primary-and-provider-identity"></a>检索主标识和提供程序标识

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
服务提供商（通常是通讯簿提供程序）可以选择提供可用于表示各种情况下的会话的标识。 三个属性描述提供程序的标识：
  
- **PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md) 
    
- **PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))  
    
- **PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))  
    
这些属性设置为对应的标识对象（通常为消息用户）的条目标识符、显示名称和搜索键。 提供标识的提供程序还会在 [PidTagResourceFlags](pidtagresourceflags-canonical-property.md) STATUS_PRIMARY_IDENTITY属性 **中设置PR_RESOURCE_FLAGS (** 标记) 标记。
  
根据您的需要，您可能会使用特定提供程序的标识或会话的主标识。 还可以将提供程序的标识用于显示目的或检索属性，如 PR_RESOURCE_PATH ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)) 。  **PR_RESOURCE_PATH**，如果设置，则包含提供程序使用或创建的文件的路径。 在 **PR_RESOURCE_PATH** 与会话用户相关的文件时，检索提供主标识的提供程序的 PR_RESOURCE_PATH 属性。 
  
 **检索特定提供程序的标识**
  
1. 调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表。 
    
2. 使用 [SPropertyRestriction](spropertyrestriction.md) 结构构建限制，以将 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 列与指定提供程序的名称相匹配。 
    
3. 调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以查找提供程序的行。 提供程序的标识将存储在 **PR_IDENTITY_ENTRYID列（** 如果存在）。 
    
 **检索会话的主标识**
  
- 调用 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md)。 **QueryIdentity** 基于状态表中某STATUS_PRIMARY_IDENTITY行的 PR_RESOURCE_FLAGS 列是否存在值来建立会话标识。 如果没有一个状态行设置了此值 **，QueryIdentity** 会向第一个设置这三个状态PR_IDENTITY标识。 如果没有服务提供商提供标识 **，QueryIdentity** 将返回MAPI_W_NO_SERVICE。 发生这种情况时，您应该创建一个字符串来表示可作为主标识的通用用户。 
    
 **显式设置会话的主标识**
  
- 调用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)。 传递 **目标服务提供商的 MAPIUID。** 
    

