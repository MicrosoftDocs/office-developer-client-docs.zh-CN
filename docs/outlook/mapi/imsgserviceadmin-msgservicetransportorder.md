---
title: IMsgServiceAdminMsgServiceTransportOrder
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.MsgServiceTransportOrder
api_type:
- COM
ms.assetid: c57ada0e-b9a1-496b-8548-75686d8cba4e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 559f1c609000608d0eb920a0240ac8848e4bc2a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570791"
---
# <a name="imsgserviceadminmsgservicetransportorder"></a>IMsgServiceAdmin::MsgServiceTransportOrder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置中的传输提供程序调用将邮件传递的顺序。
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a>参数

 _cUID_
  
> [in]_LpUIDList_参数中的唯一标识符的计数。 
    
 _lpUIDList_
  
> [in]一个指向代表传输提供程序的唯一标识符的数组。 该数组中的当前配置文件配置每个传输提供程序包含一个标识符。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置传输顺序。
    
MAPI_E_BUSY 
  
> _CUID_参数中的值不同于实际配置文件中的传输提供程序的数目。 
    
MAPI_E_NOT_FOUND 
  
> 一个或多个_lpUIDList_参数中传递的[MAPIUID](mapiuid.md)结构不引用当前配置文件中的传输提供程序。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::MsgServiceTransportOrder**方法设置配置文件中的传输提供程序传递的顺序。 _LpUIDList_参数必须包含传输提供程序条目标识符从[IMsgServiceAdmin 从返回的表的**PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取一个已排序的列表：GetProviderTable](imsgserviceadmin-getprovidertable.md)方法。 客户端应用程序必须_lpUIDList_中传递的完整列表。
  
 **SetTransportOrder**覆盖传输提供程序首选项，如**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_XP_PREFER_LAST 标志。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

