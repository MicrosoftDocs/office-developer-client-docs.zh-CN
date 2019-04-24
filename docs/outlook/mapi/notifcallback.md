---
title: NOTIFCALLBACK
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFCALLBACK
api_type:
- COM
ms.assetid: 416008b4-13aa-4387-8c12-f8f2ca252391
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e2a1a582894e082722d73422fc8bafe34c4230c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334473"
---
# <a name="notifcallback"></a>NOTIFCALLBACK

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于接收事件通知的 MAPI 调用的回调函数。 仅当在通过调用[HrAllocAdviseSink](hrallocadvisesink.md)函数创建的通知接收器对象中包装时, 才能使用此回调函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|定义的函数实现者:  <br/> |客户端应用程序和服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
```cpp
ULONG (STDAPICALLTYPE NOTIFCALLBACK)(
  LPVOID lpvContext,
  ULONG cNotification,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> 实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。 此值可以表示对客户端应用程序或服务提供程序的重要性的地址。 通常, 对于 c + + 代码, _lpvContext_参数表示指向 c + + 对象的指针。 
    
 _cNotification_
  
> 实时由_lpNotifications_参数指示的数组中的事件通知数。 
    
 _lpNotifications_
  
> 排除指向此函数写入包含事件通知的[通知](notification.md)结构数组的位置的指针。 
    
## <a name="return-value"></a>返回值

**NOTIFCALLBACK**函数原型的有效返回值集取决于函数是否由客户端应用程序或服务提供程序实现。 客户端应始终返回 S_OK。 提供程序可以返回 S_OK 或 CALLBACK_DISCONTINUE。 
  
## <a name="remarks"></a>注解

CALLBACK_DISCONTINUE 是仅适用于同步回调函数的有效返回值;它请求 MAPI 立即停止处理此通知的回调。 当返回 CALLBACK_DISCONTINUE 时, MAPI 在从[IMAPISupport:: NOTIFY](imapisupport-notify.md)返回时将_lpUlFlags_参数设置为 NOTIFY_CANCELED。 
  
以下是同步回调函数可以执行的操作的限制:
  
- 它不会导致生成另一个同步通知。
    
- 它无法显示用户界面。
    
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)

