---
title: IProviderAdminDeleteProvider
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.DeleteProvider
api_type:
- COM
ms.assetid: 0065b50f-95f6-4af1-81c2-a73e5111eecf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db09b44bd8eeeb3ab56513b1b9c2cab69f776002
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590083"
---
# <a name="iprovideradmindeleteprovider"></a>IProviderAdmin::DeleteProvider

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除消息服务的服务提供商。
  
```cpp
HRESULT DeleteProvider(
  LPMAPIUID lpUID
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [传入、 传出]一个指向[MAPIUID](mapiuid.md)结构，其中包含代表要删除的提供程序的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 提供程序已成功删除从邮件服务。
    
MAPI_E_NOT_FOUND 
  
> 无法识别**MAPIUID** _lpUID_参数指向。 
    
## <a name="remarks"></a>注解

**IProviderAdmin::DeleteProvider**方法删除消息服务的服务提供商。 **DeleteProvider**确定服务提供商删除匹配**MAPIUID**结构所指的_lpUID_注册的活动服务提供商的标识符的设置。 
  
大多数消息服务不允许使用配置文件时要删除的提供程序。 如果要删除的提供程序正在使用中， **DeleteProvider**将其标记为删除而不是立即删除并返回 S_OK。 不再使用提供程序时，则将其删除。 
  
 从服务中删除提供程序之前， **DeleteProvider**调用消息服务的入口点函数。 _UlContext_参数设置为 MSG_SERVICE_PROVIDER_DELETE。 消息服务入口点函数执行以下任务： 
  
- 删除服务提供程序。
    
- 删除服务提供商的配置文件一节。
    
删除提供程序后，不是再次调用消息服务入口点函数。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)

