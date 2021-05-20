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
  
为线程安全创建包装现有建议接收器的建议接收器。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
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
  
> [in]指向要封装的建议接收器的指针。 
    
 _lppAdviseSink_
  
> [out]指向新建议接收器的指针，该接收器包装  _lpAdviseSink_ 参数指向的建议接收器。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

包装器的目的是确保通知在调用 **HrThisThreadAdviseSink** 函数的同一线程上调用。 此函数用于保护必须在特定线程上运行的通知回调。 
  
客户端应用程序应该使用 **HrThisThreadAdviseSink** 来限制生成通知的时间，即调用客户端在之前的 **Advise** 调用中传递的建议接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法。 如果允许任意生成通知，通知实现可能会强制客户端执行多线程操作（如果不适合）。 例如，客户端可能使用不支持多线程调用的库（如 Microsoft Foundation 类库之一）。 其他线程上的通知会使此类客户端难以测试且容易出错。 
  
 **HrThisThreadAdviseSink** 确保仅在以下适当时间发生 **OnNotify** 调用： 
  
- 在处理对任意 MAPI 方法的调用期间。 
    
- 在处理邮件Windows期间。 
    
当 **实现 HrThisThreadAdviseSink** 时，在任何线程上对新通知接收器 **的 OnNotify** 方法的任何调用都会导致原始通知方法在调用 **HrThisThreadAdviseSink** 的线程上执行。 
  
有关通知和通知接收器详细信息，请参阅 [MAPI](event-notification-in-mapi.md) 中的事件通知 [和实现通知接收对象](implementing-an-advise-sink-object.md)。 
  

