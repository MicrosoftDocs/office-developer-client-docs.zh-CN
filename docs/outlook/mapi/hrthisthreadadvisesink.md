---
title: HrThisThreadAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrThisThreadAdviseSink
api_type:
- COM
ms.assetid: 12c07302-472f-4e4f-8087-1bdf0dc09a5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0fb867d662064dfe5ff7759dba4b36a4635a2914
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427725"
---
# <a name="hrthisthreadadvisesink"></a>HrThisThreadAdviseSink

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建为线程安全包装现有建议接收器的通知接收器。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrThisThreadAdviseSink(
  LPMAPIADVISESINK lpAdviseSink,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a>参数

 _lpAdviseSink_
  
> 实时指向要包装的通知接收器的指针。 
    
 _lppAdviseSink_
  
> 排除指向新的通知接收器的指针, 该通知接收器将由_lpAdviseSink_参数指向的通知接收器进行包装。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

包装的目的是确保在调用**HrThisThreadAdviseSink**函数的同一线程上调用通知。 此函数用于保护必须在特定线程上运行的通知回调。 
  
客户端应用程序应使用**HrThisThreadAdviseSink**来限制生成通知的时间, 即在上一次建议中对客户端传递的建议接收器对象的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法进行调用**** 调用。 如果允许任意生成通知, 则通知实现可能会在不适当的情况下强制客户端进入多线程操作。 例如, 客户端可能使用不支持多线程调用的某个库, 如 Microsoft 基础类库中的一个。 在不同线程上的通知将导致客户端难以测试且容易出错。 
  
 **HrThisThreadAdviseSink**确保**OnNotify**调用仅在以下适当的时间发生: 
  
- 在处理对任何 MAPI 方法的调用的过程中。 
    
- 在 Windows 消息的处理过程中。 
    
在实现**HrThisThreadAdviseSink**时, 任何线程上对新的通知接收器的**OnNotify**方法的任何调用都会导致在调用**HrThisThreadAdviseSink**的线程上执行原始通知方法。 
  
有关通知和建议接收器的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[实现建议接收器对象](implementing-an-advise-sink-object.md)。 
  

