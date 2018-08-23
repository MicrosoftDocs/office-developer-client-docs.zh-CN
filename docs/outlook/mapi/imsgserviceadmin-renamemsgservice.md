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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a6eba20fb346f53052808abf8fcae8993d423d34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589558"
---
# <a name="imsgserviceadminrenamemsgservice"></a>IMsgServiceAdmin::RenameMsgService

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
已弃用。 将新的名称分配给邮件服务。 
  
```cpp
HRESULT RenameMsgService(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPSTR lpszDisplayName
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要重命名的消息服务的唯一标识符。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpszDisplayName_
  
> [in]一个指向邮件服务的新名称。
    
## <a name="return-value"></a>返回值

MAPI_E_NO_SUPPORT 
  
> MAPI 不支持重命名此消息服务。 **RenameMsgService**始终返回此值。 
    
## <a name="remarks"></a>注解

分配给消息服务的新名称，客户端应使用消息服务的**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性。 消息服务中的服务提供商的名称将存储在其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

