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
  
设置调用传输提供程序以传递邮件的顺序。
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a>参数

 _cUID_
  
> [in]  _lpUIDList_ 参数中的唯一标识符计数。 
    
 _lpUIDList_
  
> [in]指向表示传输提供程序的唯一标识符数组的指针。 数组包含当前配置文件中配置的每个传输提供程序的一个标识符。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置传输顺序。
    
MAPI_E_BUSY 
  
> _cUID_ 参数中的值与配置文件中实际传输提供程序的数量不同。 
    
MAPI_E_NOT_FOUND 
  
> 在 _lpUIDList_ 参数中传递的一个或多个 [MAPIUID](mapiuid.md)结构不引用配置文件中的当前传输提供程序。 
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：MsgServiceTransportOrder** 方法设置配置文件中传输提供程序的传递顺序。 _lpUIDList_ 参数必须包含从从 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的表的 **PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取的传输提供程序条目标识符的排序列表。 客户端应用程序必须在  _lpUIDList 中传递完整列表_。
  
 **SetTransportOrder** 重写传输提供程序首选项，如 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 设置 STATUS_XP_PREFER_LAST 标志。  
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

