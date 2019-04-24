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
ms.openlocfilehash: f4af3f2fd094942c48e02849c60f3e46acb1a5f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348095"
---
# <a name="hrdispatchnotifications"></a>HrDispatchNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
强制调度所有已排队的通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrDispatchNotifications(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已调度所有排队的通知。
    
MAPI_E_USER_CANCEL
  
> 已收到 WM_QUIT、WM_QUERYENDSESSION 或 WM_ENDSESSION。
    
MAPI_E_NOT_INITIALIZED
  
> MAPI 未初始化。
    
## <a name="remarks"></a>注解

**HrDispatchNotifications**函数会导致 mapi 调度当前在 MAPI 通知引擎中排队的所有通知, 而无需等待邮件调度。 这可能会对内存使用率产生有益的影响。 有关详细信息, 请参阅[强制发出通知](forcing-a-notification.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

某些应用程序使用 Windows [PeekMessage](https://msdn.microsoft.com/library/ms644943.aspx)和[DispatchMessage](https://msdn.microsoft.com/library/ms644934.aspx)函数在超时循环中等待通知消息。 除了最快的平台之外, 此类应用程序可能会遇到较差的性能甚至通知。 使用**HrDispatchNotifications**不仅可以减少代码, 还可提高性能。 
  

