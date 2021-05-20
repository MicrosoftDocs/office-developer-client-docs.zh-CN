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
  
指定邮件服务作为配置文件的主标识的供应商。
  
```cpp
HRESULT SetPrimaryIdentity(
  LPMAPIUID lpUID,
  ULONG ulFlags  
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含提供主标识的邮件服务的唯一标识符或 NULL，指示 **SetPrimaryIdentity** 应清除当前标识。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件服务已成功分配主标识的供应商。
    
MAPI_E_NO_ACCESS 
  
> **SetPrimaryIdentity** 尝试指定在其 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)属性中设置了 **SERVICE_NO_PRIMARY_IDENTITY** 标志) 服务。
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：SetPrimaryIdentity** 方法将邮件服务建立为配置文件的主标识的供应商。 主标识通常是登录到邮件服务的用户。 它由三个属性表示： 
  
- **PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 
    
- **PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId)](pidtagidentityentryid-canonical-property.md)
    
- **PR_IDENTITY_SEARCH_KEY (** [PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 
    
指定邮件服务中的每个服务提供商将这三个属性显示名称提供主标识的邮件用户的名称、条目标识符和搜索密钥。 客户端可以通过调用 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md) 方法检索主标识的条目标识符。 
  
对于 **PR_RESOURCE_FLAGS** 主标识的邮件服务成员STATUS_PRIMARY_IDENTITY，将 PR_RESOURCE_FLAGS 属性设置为 SERVICE_PRIMARY_IDENTITY，并针对邮件服务设置此属性。 当服务提供商无法提供其邮件服务的主标识时，它会将PR_RESOURCE_FLAGS **设置STATUS_NO_PRIMARY_IDENTITY。** **SetPrimaryIdentity** **PR_RESOURCE_FLAGS未** 提供主标识的每个邮件服务的 SERVICE_NO_PRIMARY_IDENTITY。 
  
当客户端登录到服务时，MAPI 具有相关信息的每个邮件服务提供商都可以为每个用户建立标识。 但是，由于 MAPI 支持针对每个 MAPI 会话连接到多个服务提供商，因此对于整个 MAPI 会话的特定用户标识没有明确的定义;用户的标识取决于涉及的服务。 客户端可以调用 **SetPrimaryIdentity，** 以将邮件服务为用户建立的众多标识之一指定为该用户的主标识。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession::QueryIdentity](imapisession-queryidentity.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

