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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b237a57dfea020c7bfcb66d49d43428c1f6506c2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430362"
---
# <a name="imsgserviceadminsetprimaryidentity"></a>IMsgServiceAdmin::SetPrimaryIdentity

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件服务指定为配置文件的主标识的供应商。
  
```cpp
HRESULT SetPrimaryIdentity(
  LPMAPIUID lpUID,
  ULONG ulFlags  
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> 实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含用于提供主标识的邮件服务的唯一标识符, 或者为 NULL, 这表示**SetPrimaryIdentity**应清除当前标识。 
    
 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功为邮件服务分配了主要标识的提供商。
    
MAPI_E_NO_ACCESS 
  
> **SetPrimaryIdentity**尝试指定在其**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 SERVICE_NO_PRIMARY_IDENTITY 标志的邮件服务。
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin:: SetPrimaryIdentity**方法将邮件服务建立为配置文件主标识的供应商。 主要标识通常是登录到邮件服务的用户。 它由三个属性表示: 
  
- **PR_IDENTITY_DISPLAY**([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))
    
- **PR_IDENTITY_ENTRYID**([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))
    
- **PR_IDENTITY_SEARCH_KEY**([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))
    
指定邮件服务中的每个服务提供程序将这三个属性设置为提供主要标识的邮件用户的显示名称、条目标识符和搜索关键字。 客户端可以通过调用[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)方法来检索主标识的条目标识符。 
  
对于提供主要标识的邮件服务的成员的每个提供程序, **PR_RESOURCE_FLAGS**属性设置为 STATUS_PRIMARY_IDENTITY, 对于邮件服务, 则设置为 SERVICE_PRIMARY_IDENTITY。 如果服务提供商无法为其邮件服务提供主标识, 则会将**PR_RESOURCE_FLAGS**设置为 STATUS_NO_PRIMARY_IDENTITY。 **SetPrimaryIdentity**设置不向 SERVICE_NO_PRIMARY_IDENTITY 提供主标识的每个邮件服务的**PR_RESOURCE_FLAGS**属性。 
  
MAPI 中的每个邮件服务提供程序都可以在客户端登录到该服务时为每个用户建立标识。 但是, 由于 mapi 支持与多个服务提供商的连接, 为每个 mapi 会话提供一个特定用户的标识, 而不是作为一个整体为 mapi 会话定义用户的标识取决于所涉及的服务。 客户端可以调用**SetPrimaryIdentity** , 以将邮件服务为用户建立的许多标识之一指定为该用户的主要标识。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::QueryIdentity](imapisession-queryidentity.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

