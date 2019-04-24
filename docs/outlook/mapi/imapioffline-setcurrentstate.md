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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321208"
---
# <a name="imapiofflinesetcurrentstate"></a>IMAPIOffline::SetCurrentState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将脱机对象的当前状态设置为 "联机" 或 "脱机"。
  
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
  
> 实时修改此调用的行为。 受支持的值包括：
    
MAPIOFFLINE_FLAG_BLOCK
  
> 将_ulFlags_设置为此值将阻止**SetCurrentState**调用, 直至状态更改完成。 默认情况下, 转换会异步进行。 当以异步方式进行转换时, 所有**SetCurrentState**调用将返回**E_PENDING** , 直到更改完成。 
    
MAPIOFFLINE_FLAG_DEFAULT
  
> 在不阻止的情况下设置当前状态。
    
 _ulMask_
  
> 实时要更改的状态部分。 唯一受支持的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。
    
 _ulState_
  
> 实时要更改为的状态。 它必须是以下两个值之一:
    
MAPIOFFLINE_STATE_ONLINE
  
> 
    
MAPIOFFLINE_STATE_OFFLINE
  
> 
    
 _保护_
  
> 此参数是为 Outlook 内部使用而保留的, 不受支持。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功更改脱机对象的状态。
    
E_PENDING
  
> 这表示脱机对象的状态是异步更改的。 在早期**SetCurrentState**调用中将_ulFlags_设置为 MAPIOFFLINE_FLAG_BLOCK, 随后的任何**SetCurrentState**调用都将返回此值, 直到异步状态更改完成。 
    
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)


[MAPI 常量](mapi-constants.md)

