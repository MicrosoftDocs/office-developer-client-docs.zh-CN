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
# <a name="mapioffline_adviseinfo"></a>MAPIOFFLINE_ADVISEINFO
 
**适用于**：Outlook 2013 | Outlook 2016 
  
向 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 提供为脱机对象注册回调的信息。 
  
## <a name="quick-info"></a>快速信息

请参阅 **IMAPIOfflineMgr：：Advise**。 
  
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

_ulSize：MAPIOFFLINE_ADVISEINFO。_  
    
_ulClientToken：_ 客户端定义的有关回调的令牌。 它是传递到 **[IMAPIOfflineNotify：：Notify](imapiofflinenotify-notify.md)****[的](mapioffline_notify.md)** MAPIOFFLINE_NOTIFY 结构的 *ulClientToken* 成员。 
    
_CallbackType：_ 要进行回调的类型。
    
   -  MAPIOFFLINE_CALLBACK_TYPE_NOTIFY 
    
   - 回调的类型是通知。 这是唯一受支持的回调类型。  *pCallback*  必须指示 **[接口 IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
    
_pCallback：_ 用于回调的接口。 这是客户端对 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的实现。 
    
_ulAdviseTypes：_ 建议类型，由建议条件标识。 唯一受支持的类型是 MAPIOFFLINE_ADVISE_TYPE_STATECHANGE。
    
_ulStateMask：_ 唯一受支持的状态是 MAPIOFFLINE_STATE_ALL。
    
## <a name="see-also"></a>另请参阅

- [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)
- [关于脱机状态 API](about-the-offline-state-api.md) 
- [MAPI 常量](mapi-constants.md) 
- [MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)

