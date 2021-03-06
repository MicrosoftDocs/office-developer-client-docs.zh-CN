---
title: IMsgServiceAdminRenameMsgService
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.RenameMsgService
api_type:
- COM
ms.assetid: eba0e7f2-03c1-4713-aa36-3d0b398cd197
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2f0f1fb94ea36512bbc40df8a4877e89d2613a25
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422101"
---
# <a name="imsgserviceadminrenamemsgservice"></a>IMsgServiceAdmin::RenameMsgService

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
已弃用。 为邮件服务分配新名称。 
  
```cpp
HRESULT RenameMsgService(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPSTR lpszDisplayName
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要重命名的邮件服务的唯一标识符。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpszDisplayName_
  
> [in]指向邮件服务的新名称的指针。
    
## <a name="return-value"></a>返回值

MAPI_E_NO_SUPPORT 
  
> MAPI 不支持重命名此消息服务。 **RenameMsgService** 始终返回此值。 
    
## <a name="remarks"></a>备注

若要向邮件服务分配新名称，客户端应PR_SERVICE_NAME ( [PidTagServiceName) PidTagServiceName](pidtagservicename-canonical-property.md)属性。 邮件服务中的服务提供商的名称存储在[PidTagDisplayName 属性PR_DISPLAY_NAME (PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 中。  
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

