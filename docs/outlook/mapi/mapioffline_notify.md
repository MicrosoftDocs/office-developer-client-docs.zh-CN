---
title: MAPIOFFLINE_NOTIFY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e03c5a87-4513-2133-ae0a-11d242f80e4b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c5480a8f5e008c01c7ab8141317f5f19547ab10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270292"
---
# <a name="mapiofflinenotify"></a>MAPIOFFLINE_NOTIFY

**适用于**：Outlook 2013 | Outlook 2016 
  
这是连接状态更改的通知。 它指示已更改的连接状态部分、旧的连接状态和新的连接状态。
  
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
  
> **MAPIOFFLINE_NOTIFY**结构的大小。 
    
 _NotifyType_
  
> 通知的类型。 请注意, 仅支持更改连接状态通知;唯一受支持的值是:
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE
    
 _ulClientToken_
  
> 客户端在**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 的**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 结构中定义的令牌。 
    
 _ulMask_
  
> 已更改的连接状态部分。 唯一受支持的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulStateOld_
  
> 旧的连接状态。 唯一受支持的值是:
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
 _ulStateNew_
  
> 新的连接状态。 唯一受支持的值是:
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
## <a name="remarks"></a>注解

脱机状态 API 仅支持联机/脱机更改的通知。 在检查实际更改之前, 客户端必须先检查 Outlook 是否返回以下值:
  
1.  *NotifyType*的值为 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE。 在这种情况下, 客户端可以假定更改是连接状态更改,*信息*的结构*StateChange* 。 
    
2.  *ulMask*的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。 在这种情况下, 客户端可以假定更改为联机/脱机连接状态更改, 并可继续检查*ulStateOld*和*ulStateNew* 。 
    
Outlook 可能会向客户端通知不受支持的其他更改。 在这种情况下, *NotifyType*不会是前面提到的三个值中的** 任何一个, 否则, 客户端必须忽略*Info*中的其余数据。 
  
## <a name="see-also"></a>另请参阅

- [关于脱机状态 API](about-the-offline-state-api.md)  
- [MAPI 常量](mapi-constants.md)  
- [MAPIOFFLINE_NOTIFY_TYPE](mapioffline_notify_type.md)

