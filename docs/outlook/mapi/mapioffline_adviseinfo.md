---
title: MAPIOFFLINE_ADVISEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 20a46c69-d6ae-7d17-f8af-12952867d342
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82869fa479ebe8a4d7b1881cec5d5c243b7d7957
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565093"
---
# <a name="mapiofflineadviseinfo"></a>MAPIOFFLINE_ADVISEINFO
 
**适用于**： Outlook 2013 |Outlook 2016 
  
向**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 注册回调脱机对象提供信息。 
  
## <a name="quick-info"></a>快速信息

请参阅**IMAPIOfflineMgr::Advise**。 
  
```cpp
typedef struct 
{ 
      ULONG                   ulSize; 
      ULONG                   ulClientToken; 
      MAPIOFFLINE_CALLBACK_TYPE     CallbackType; 
      IUnknown*               pCallback; 
      ULONG                   ulAdviseTypes; 
      ULONG                   ulStateMask; 
} MAPIOFFLINE_ADVISEINFO;
```

## <a name="members"></a>Members

_ulSize_: **MAPIOFFLINE_ADVISEINFO**的大小。 
    
_ulClientToken_： 定义由客户端有关回调令牌。 它是传递给**[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** 结构的*ulClientToken*成员。 
    
_CallbackType_： 回调进行的类型。
    
   -  MAPIOFFLINE_CALLBACK_TYPE_NOTIFY 
    
   - 回调的类型是由通知。 这是回调的唯一受支持类型。  *pCallback*必须指明**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的接口。 
    
_pCallback_： 接口用于回调。 这是**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的客户端的实现。 
    
_ulAdviseTypes_: advise，如标识的条件的建议的类型。 MAPIOFFLINE_ADVISE_TYPE_STATECHANGE 唯一支持的类型。
    
_ulStateMask_： 只有受支持的状态是 MAPIOFFLINE_STATE_ALL。
    
## <a name="see-also"></a>另请参阅

- [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)
- [关于脱机状态 API](about-the-offline-state-api.md) 
- [MAPI 常量](mapi-constants.md) 
- [MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)

