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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 28dbbb98c9810bb688b9ecdd730ef6c4ada5f60b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404860"
---
# <a name="iprovideradmindeleteprovider"></a>IProviderAdmin::DeleteProvider

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从邮件服务中删除服务提供程序。
  
```cpp
HRESULT DeleteProvider(
  LPMAPIUID lpUID
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in, out]指向[MAPIUID](mapiuid.md)结构的指针, 该对象包含表示要删除的提供程序的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功从邮件服务中删除提供程序。
    
MAPI_E_NOT_FOUND 
  
> 无法识别_lpUID_参数指向的**MAPIUID** 。 
    
## <a name="remarks"></a>说明

**IProviderAdmin::D eleteprovider**方法从邮件服务中删除服务提供程序。 **DeleteProvider**确定要删除的服务提供程序, 方法是将_lpUID_所指向的**MAPIUID**结构与活动服务提供商注册的一组标识符相匹配。 
  
大多数邮件服务不允许在配置文件正在使用时删除提供程序。 如果要删除的提供程序正在使用中, **DeleteProvider**会将其标记为删除, 而不是立即删除它并返回 S_OK。 如果不再使用该提供程序, 则将其删除。 
  
 在从服务中删除提供程序之前, **DeleteProvider**调用邮件服务的入口点函数。 _ulContext_参数设置为 MSG_SERVICE_PROVIDER_DELETE。 邮件服务入口点函数执行以下任务: 
  
- 删除服务提供程序。
    
- 删除服务提供程序的配置文件部分。
    
删除提供程序后, 不会再次调用邮件服务入口点函数。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)

