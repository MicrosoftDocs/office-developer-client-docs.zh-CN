---
title: HrDispatchNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDispatchNotifications
api_type:
- COM
ms.assetid: 42ec4266-67b9-416e-8b9b-163c95011626
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28afa338b37e747ed441a8767981b7e63808e741
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775164"
---
# <a name="hrdispatchnotifications"></a>HrDispatchNotifications

  
  
**适用于**： Outlook 
  
强制调度的所有排队的通知。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrDispatchNotifications(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已调度所有排队的通知。
    
MAPI_E_USER_CANCEL
  
> 收到 WM_QUIT、 WM_QUERYENDSESSION 或 WM_ENDSESSION。
    
MAPI_E_NOT_INITIALIZED
  
> 未初始化 MAPI。
    
## <a name="remarks"></a>说明

**HrDispatchNotifications**函数会导致 MAPI 调度当前无需等待消息调度排队 MAPI 通知引擎中的所有通知。 这可能会产生对内存使用率有益影响。 有关详细信息，请参阅[强制通知](forcing-a-notification.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

某些应用程序等待超时循环使用 Windows [PeekMessage](http://msdn.microsoft.com/en-us/library/ms644943.aspx)和[DispatchMessage](http://msdn.microsoft.com/en-us/library/ms644934.aspx)函数一封通知邮件。 对所有但最快平台，此类应用程序可能会遇到性能不佳或偶数瓶颈的通知。 使用**HrDispatchNotifications**不仅减少了代码，提高了性能。 
  

