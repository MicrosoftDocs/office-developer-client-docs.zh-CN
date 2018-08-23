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
ms.openlocfilehash: 17b038fea2dd1614f94f005e32b9e6ba4423dbda
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566262"
---
# <a name="notifcallback"></a>NOTIFCALLBACK

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
定义一个 MAPI 调用发送事件通知的回调函数。 仅，可通过调用[HrAllocAdviseSink](hrallocadvisesink.md)函数创建 advise 接收器对象中自动换行时使用此回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实施定义的函数：  <br/> |客户端应用程序和服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
ULONG (STDAPICALLTYPE NOTIFCALLBACK)(
  LPVOID lpvContext,
  ULONG cNotification,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> [in]MAPI 调用它时，为任意值的指针传递给回调函数。 此值可表示的有效位倍数客户端应用程序或服务提供商的地址。 通常，c + + 代码_lpvContext_参数对 c + + 对象表示的指针。 
    
 _cNotification_
  
> [in]由_lpNotifications_参数指示在阵列中的事件通知的计数。 
    
 _lpNotifications_
  
> [输出]其中此函数写入的[通知](notification.md)结构数组的位置的指针包含事件通知。 
    
## <a name="return-value"></a>返回值

**NOTIFCALLBACK**函数原型返回值有效的集取决于是否由客户端应用程序或服务提供商实现函数。 客户端应始终返回 S_OK。 提供程序可以返回 S_OK 或 CALLBACK_DISCONTINUE。 
  
## <a name="remarks"></a>注解

CALLBACK_DISCONTINUE 是同步的回调函数仅; 有效的返回值它请求 MAPI 立即停止处理此通知的回调。 返回 CALLBACK_DISCONTINUE 时，MAPI _lpUlFlags_将参数设置为 NOTIFY_CANCELED 从[IMAPISupport::Notify](imapisupport-notify.md)返回时。 
  
下面是同步的回调函数可以执行的操作的限制：
  
- 它不会导致要生成的其他同步通知。
    
- 它不能显示用户界面。
    
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)

