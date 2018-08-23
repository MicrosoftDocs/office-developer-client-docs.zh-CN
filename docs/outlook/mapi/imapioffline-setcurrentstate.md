---
title: IMAPIOfflineSetCurrentState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.SetCurrentState
api_type:
- COM
ms.assetid: c0aa0df2-79f9-2558-7eb6-accae9bef4b2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 13a4cf401cf51241a52401668eef008d65aa5459
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567137"
---
# <a name="imapiofflinesetcurrentstate"></a>IMAPIOffline::SetCurrentState

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置为联机或脱机脱机对象的当前状态。
  
```cpp
HRESULT SetCurrentState( 
    ULONG ulFlags, 
    ULONG ulMask, 
    ULONG ulState, 
    void* pReserved 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]修改此呼叫的行为。 支持的值包括：
    
MAPIOFFLINE_FLAG_BLOCK
  
> 此值设置为_ulFlags_将阻止**SetCurrentState**呼叫，直至完成状态更改。 默认情况下切换异步会发生。 转换异步后发生，所有**SetCurrentState**呼叫将都返回**E_PENDING** ，直至完成更改。 
    
MAPIOFFLINE_FLAG_DEFAULT
  
> 不阻止设置的当前状态。
    
 _ulMask_
  
> [in]状态更改的一部分。 仅受支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulState_
  
> [in]要更改的状态。 它必须是这两个值之一：
    
MAPIOFFLINE_STATE_ONLINE
  
> 
    
MAPIOFFLINE_STATE_OFFLINE
  
> 
    
 _保留_
  
> 此参数仅供 Outlook 内部使用，不支持。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功更改脱机对象的状态。
    
E_PENDING
  
> 这指示正在异步更改脱机对象的状态。 在以前**SetCurrentState**调用， _ulFlags_设置为 MAPIOFFLINE_FLAG_BLOCK 和任何后续**SetCurrentState**调用异步状态更改完成之前将返回此值时，将发生这种情况。 
    
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)


[MAPI 常量](mapi-constants.md)

