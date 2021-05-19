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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434016"
---
# <a name="notifcallback"></a>NOTIFCALLBACK

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义 MAPI 调用以发送事件通知的回调函数。 此回调函数只能在封装在通过调用 [HrAllocAdviseSink](hrallocadvisesink.md) 函数创建的通知接收器对象中时使用。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|定义的函数实现方：  <br/> |客户端应用程序和服务提供商  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
```cpp
ULONG (STDAPICALLTYPE NOTIFCALLBACK)(
  LPVOID lpvContext,
  ULONG cNotification,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> [in]指向 MAPI 调用回调函数时传递给回调函数的任意值的指针。 此值可以表示对客户端应用程序或服务提供商有意义的地址。 通常，对于 C++ 代码  _，lpvContext_ 参数表示指向 C++ 对象的指针。 
    
 _cNotification_
  
> [in]  _lpNotifications_ 参数指示的数组中的事件通知计数。 
    
 _lpNotifications_
  
> [out]指向此函数写入包含事件通知 [的 NOTIFICATION](notification.md) 结构数组的位置的指针。 
    
## <a name="return-value"></a>返回值

**NOTIFCALLBACK** 函数原型的有效返回值集取决于函数是由客户端应用程序或服务提供商实现的。 客户端应始终返回S_OK。 提供程序可以返回S_OK或CALLBACK_DISCONTINUE。 
  
## <a name="remarks"></a>备注

CALLBACK_DISCONTINUE只是同步回调函数的有效返回值;它请求 MAPI 立即停止处理此通知的回调。 返回CALLBACK_DISCONTINUE时，MAPI 将 _lpUlFlags_ 参数NOTIFY_CANCELED [从 IMAPISupport：：Notify 返回时返回。](imapisupport-notify.md) 
  
以下是同步回调函数可以执行哪些操作的限制：
  
- 它不能生成另一个同步通知。
    
- 它无法显示用户界面。
    
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)

