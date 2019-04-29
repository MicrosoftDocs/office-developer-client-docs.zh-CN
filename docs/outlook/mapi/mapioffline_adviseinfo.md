---
title: MAPIOFFLINE_ADVISEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 20a46c69-d6ae-7d17-f8af-12952867d342
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3cb110fdcbbd88e494c44ba2ed73cc26674638ca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420022"
---
# <a name="mapiofflineadviseinfo"></a>MAPIOFFLINE_ADVISEINFO
 
**适用于**：Outlook 2013 | Outlook 2016 
  
向**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 为脱机对象注册回调的信息。 
  
## <a name="quick-info"></a>快速信息

请参阅**IMAPIOfflineMgr:: Advise**。 
  
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
    
_ulClientToken_: 客户端定义的有关回调的令牌。 它是传递给**[IMAPIOfflineNotify:: NOTIFY](imapiofflinenotify-notify.md)** 的**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** 结构的*ulClientToken*成员。 
    
_CallbackType_: 要进行的回调类型。
    
   -  MAPIOFFLINE_CALLBACK_TYPE_NOTIFY 
    
   - 回调的类型为 "通知"。 这是唯一受支持的回调类型。  *pCallback*必须指示接口**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
    
_pCallback_: 用于回呼的接口。 这是客户端的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 实现。 
    
_ulAdviseTypes_: 建议的类型, 由建议的条件标识。 唯一受支持的类型为 MAPIOFFLINE_ADVISE_TYPE_STATECHANGE。
    
_ulStateMask_: 唯一受支持的状态是 MAPIOFFLINE_STATE_ALL。
    
## <a name="see-also"></a>另请参阅

- [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)
- [关于脱机状态 API](about-the-offline-state-api.md) 
- [MAPI 常量](mapi-constants.md) 
- [MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)

