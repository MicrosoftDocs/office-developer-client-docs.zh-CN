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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0b6837b51b09ecd9a60630c613e1806cb10c1d87
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421737"
---
# <a name="imapiofflinesetcurrentstate"></a>IMAPIOffline::SetCurrentState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将脱机对象的当前状态设置为联机或脱机。
  
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
  
> [in]修改此调用的行为。 受支持的值包括：
    
MAPIOFFLINE_FLAG_BLOCK
  
> 将  _ulFlags_ 设置为此值将阻止 **SetCurrentState** 调用，直到状态更改完成。 默认情况下，切换异步进行。 异步执行转换时，所有 **SetCurrentState** 调用 **E_PENDING直到更改** 完成。 
    
MAPIOFFLINE_FLAG_DEFAULT
  
> 设置当前状态而不阻止。
    
 _ulMask_
  
> [in]要更改的状态部分。 唯一支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulState_
  
> [in]要更改为的状态。 它必须是以下两个值之一：
    
MAPIOFFLINE_STATE_ONLINE
  
> 
    
MAPIOFFLINE_STATE_OFFLINE
  
> 
    
 _pReserved_
  
> 此参数仅供Outlook内部使用，不受支持。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 脱机对象的状态已成功更改。
    
E_PENDING
  
> 这表示脱机对象的状态正在异步更改。 当在早期的 **SetCurrentState** 调用中 _将 ulFlags_ 设置为 MAPIOFFLINE_FLAG_BLOCK，并且任何后续 **SetCurrentState** 调用将返回此值，直到异步状态更改完成时，才会发生这种情况。 
    
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)


[MAPI 常量](mapi-constants.md)

