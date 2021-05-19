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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414765"
---
# <a name="mapioffline_notify"></a>MAPIOFFLINE_NOTIFY

**适用于**：Outlook 2013 | Outlook 2016 
  
这是连接状态更改的通知。 它指示已更改的连接状态部分、旧连接状态和新连接状态。
  
## <a name="quick-info"></a>快速信息

请参阅 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
  
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
  
> 结构 **MAPIOFFLINE_NOTIFY** 的大小。 
    
 _NotifyType_
  
> 通知类型。 请注意，仅支持有关连接状态更改的通知;唯一支持的值是：
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE
    
   - MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE
    
 _ulClientToken_
  
> 由客户端在 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中定义的令牌。 
    
 _ulMask_
  
> 已更改的连接状态部分。 唯一支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulStateOld_
  
> 旧连接状态。 唯一支持的值是：
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
 _ulStateNew_
  
> 新的连接状态。 唯一支持的值是：
    
   - MAPIOFFLINE_STATE_OFFLINE
    
   - MAPIOFFLINE_STATE_ONLINE
    
## <a name="remarks"></a>备注

脱机状态 API 仅支持联机/脱机更改的通知。 在检查实际更改Outlook客户端必须检查是否返回以下值：
  
1.  *NotifyType*  的值为 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START、MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE 或 MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE。 在这种情况下，客户端可以假定更改是连接状态更改，  *而 Info*  是  *StateChange 结构*  。 
    
2.  *ulMask*  具有值 MAPIOFFLINE_STATE_OFFLINE_MASK。 在这种情况下，客户端可以假定更改是联机/脱机连接状态更改，并可以继续检查  *ulStateOld*  和  *ulStateNew*  。 
    
用户可能会Outlook不支持的其他更改通知客户端。 在这种情况下  *，NotifyType*  不是前面提到的三个值中的任一个值，或者  *ulMask*  不会为 MAPIOFFLINE_STATE_OFFLINE_MASK，并且客户端必须忽略 Info 中的其余  *数据*  。 
  
## <a name="see-also"></a>另请参阅

- [关于脱机状态 API](about-the-offline-state-api.md)  
- [MAPI 常量](mapi-constants.md)  
- [MAPIOFFLINE_NOTIFY_TYPE](mapioffline_notify_type.md)

