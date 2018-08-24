---
title: MAPIOFFLINE_NOTIFY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e03c5a87-4513-2133-ae0a-11d242f80e4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b18a4ae4ee25898d1100d9763714e5be21c69fd8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580724"
---
# <a name="mapiofflinenotify"></a>MAPIOFFLINE_NOTIFY

**适用于**：Outlook 2013 | Outlook 2016 
  
这是处于连接状态更改通知。 表示已更改的连接状态、 旧的连接状态和新的连接状态的一部分。
  
## <a name="quick-info"></a>快速信息

请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
  
```cpp
typedef struct  
{ 
      ULONG ulSize; 
      MAPIOFFLINE_NOTIFY_TYPE NotifyType; 
      ULONG ulClientToken; 
      union { 
         struct 
           { 
           ULONG ulMask; 
           ULONG ulStateOld; 
           ULONG ulStateNew; 
           } StateChange; 
             } Info; 
} MAPIOFFLINE_NOTIFY;
```

## <a name="members"></a>Members

 _ulSize_
  
> **MAPIOFFLINE_NOTIFY**结构大小。 
    
 _NotifyType_
  
> 通知类型。 请注意，仅通知上的连接状态更改支持;仅支持的值包括：
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE
    
 _ulClientToken_
  
> 定义由客户端在**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 的**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 结构中的标记。 
    
 _ulMask_
  
> 连接状态的已更改的一部分。 仅受支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulStateOld_
  
> 旧的连接状态。 仅支持的值包括：
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
 _ulStateNew_
  
> 新的连接状态。 仅支持的值包括：
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
## <a name="remarks"></a>注解

脱机状态 API 支持联机/脱机更改仅通知。 客户端必须检查的 Outlook 检查实际更改之前将返回以下值：
  
1.  *NotifyType*有 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE 值。 在这种情况下，客户端可以假设已更改的更改的连接状态*信息*的*状态*的结构。 
    
2.  *ulMask*有值 MAPIOFFLINE_STATE_OFFLINE_MASK。 在这种情况下，客户端可以假定更改是联机/脱机连接的状态更改，并可以继续进行检查*ulStateOld*和*ulStateNew* 。 
    
则可能 Outlook 通知不支持其他更改的客户端。 在这种情况下， *NotifyType*不会任一前面所述的三个值或*ulMask*不会 MAPIOFFLINE_STATE_OFFLINE_MASK，和客户端必须忽略*信息*中数据的其余部分。 
  
## <a name="see-also"></a>另请参阅

- [关于脱机状态 API](about-the-offline-state-api.md)  
- [MAPI 常量](mapi-constants.md)  
- [MAPIOFFLINE_NOTIFY_TYPE](mapioffline_notify_type.md)

