---
title: IMAPISyncProgressCallbackDone
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Done
api_type:
- COM
ms.assetid: aaa8eb56-f22f-4c5a-a224-807ff001e0ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d397e12b8b24c5031e6e6d89d98134d487a815b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422346"
---
# <a name="imapisyncprogresscallbackdone"></a>IMAPISyncProgressCallback::Done

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 通知 Microsoft Outlook 同步已完成。 
  
```cpp
HRESULT Done(
  HANDLE hThreadDoneEvent, 
  HRESULT hResult
);
```

## <a name="parameters"></a>参数

 **hThreadDoneEvent**
  
> 传递回的事件, 以允许 Microsoft Outlook 关闭该句柄。 它可以是 NULL。
    
 **hResult**
  
> HRESULT, 用于指示进度的最终状态。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)

