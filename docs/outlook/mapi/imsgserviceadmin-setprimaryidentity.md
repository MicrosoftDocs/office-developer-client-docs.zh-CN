---
title: IMsgServiceAdminSetPrimaryIdentity
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.SetPrimaryIdentity
api_type:
- COM
ms.assetid: 763cab41-f6f6-4cb0-8cb8-170fdf2a92e6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 38d55f45280b0b037dc9b5cbbd0dc8809ed04e35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775861"
---
# <a name="imsgserviceadminsetprimaryidentity"></a>IMsgServiceAdmin::SetPrimaryIdentity

  
  
**适用于**： Outlook 
  
指定要配置文件的主标识的供应商的消息服务。
  
```cpp
HRESULT SetPrimaryIdentity(
  LPMAPIUID lpUID,
  ULONG ulFlags  
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要提供的主要标识的消息服务的唯一标识符或空值，指示**SetPrimaryIdentity**应清除当前的标识。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件服务已成功分配主标识供应的商。
    
MAPI_E_NO_ACCESS 
  
> **SetPrimaryIdentity**尝试指定具有其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 SERVICE_NO_PRIMARY_IDENTITY 标志的消息服务。
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin::SetPrimaryIdentity**方法建立作为的配置文件的主标识供应商的消息服务。 主标识通常是登录到邮件服务的用户。 它由三个属性表示： 
  
- **PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))
    
- **PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))
    
- **PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))
    
指定的邮件服务中的每个服务提供商将这三个属性设置为显示名称、 条目标识符和提供的主要标识的邮件用户的搜索键。 客户端可以通过调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)方法检索主标识的项标识符。 
  
**PR_RESOURCE_FLAGS**属性设置到 STATUS_PRIMARY_IDENTITY 成员提供的主要标识消息服务的每个服务提供商和 SERVICE_PRIMARY_IDENTITY 消息服务。 当服务提供程序不能提供其消息服务的主要标识时，它将**PR_RESOURCE_FLAGS**设置为 STATUS_NO_PRIMARY_IDENTITY。 **SetPrimaryIdentity**不提供对 SERVICE_NO_PRIMARY_IDENTITY 主标识每个消息服务的**PR_RESOURCE_FLAGS**属性设置。 
  
客户端登录到服务后，MAPI 对每个消息服务提供商可以为每个用户都建立标识。 但是，由于 MAPI 支持的每个 MAPI 会话到多个服务提供商的连接，因此没有严格定义的特定用户的标识作为一个整体; MAPI 会话用户的标识取决于涉及哪项服务。 客户端可以调用**SetPrimaryIdentity**要指定多个标识为用户通过消息服务建立，为该用户的主标识之一。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::QueryIdentity](imapisession-queryidentity.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

