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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3d532e0eb46daa412711344421936a58da309b7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420092"
---
# <a name="imsgserviceadminmsgservicetransportorder"></a>IMsgServiceAdmin::MsgServiceTransportOrder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置用于传递邮件的传输提供程序的调用顺序。
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a>参数

 _cUID_
  
> 实时_lpUIDList_参数中的唯一标识符的计数。 
    
 _lpUIDList_
  
> 实时指向代表传输提供程序的唯一标识符数组的指针。 对于在当前配置文件中配置的每个传输提供程序, 该数组都包含一个标识符。
    
 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置传输顺序。
    
MAPI_E_BUSY 
  
> _cUID_参数中的值不同于配置文件中实际的传输提供程序的数量。 
    
MAPI_E_NOT_FOUND 
  
> 传递到_lpUIDList_参数中的一个或多个[MAPIUID](mapiuid.md)结构不引用当前位于配置文件中的传输提供程序。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin:: MsgServiceTransportOrder**方法设置传输提供程序在配置文件中的传递顺序。 _lpUIDList_参数必须包含从 IMsgServiceAdmin 返回的表的**PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取的传输提供程序条目标识符的排序列表[::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法。 客户端应用程序必须在_lpUIDList_中传递完整列表。
  
 **SetTransportOrder**将覆盖传输提供程序首选项, 如**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置的 STATUS_XP_PREFER_LAST 标志。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

