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
ms.openlocfilehash: 3df5e012867623d1c5e8fb5c3c93103548ab97be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588382"
---
# <a name="hrthisthreadadvisesink"></a>HrThisThreadAdviseSink

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建现有通知接收器线程安全的换行通知接收器。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrThisThreadAdviseSink(
  LPMAPIADVISESINK lpAdviseSink,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a>参数

 _lpAdviseSink_
  
> [in]指向要包装通知接收器。 
    
 _lppAdviseSink_
  
> [输出]为换行通知接收器_lpAdviseSink_参数指向新通知接收器指针的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

包装的用途是确保通知称为调用**HrThisThreadAdviseSink**函数的同一线程。 此函数用于保护必须在特定线程运行的通知回调。 
  
客户端应用程序应使用**HrThisThreadAdviseSink**时将会生成通知，即，通过在客户端在上一**Advise 传递 advise 接收器对象的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法进行呼叫时限制**呼叫。 如果允许任意生成通知，通知实现可能强制客户端进入多线程操作时，不会相应。 例如，客户端可能使用库，如 Microsoft 基础类库，不支持多线程的呼叫的之一。 在不同线程上的通知应这样的客户端中测试困难，而且容易出错。 
  
 **HrThisThreadAdviseSink**可确保**OnNotify**呼叫发生仅在这些适当的时间： 
  
- 在过程中处理任何 MAPI 方法的调用。 
    
- 在 Windows 消息处理。 
    
当实现**HrThisThreadAdviseSink**时，任何调用任何线程上的新通知接收器**OnNotify**方法会导致在其调用**HrThisThreadAdviseSink**的线程上执行的原始通知方法。 
  
有关通知的详细信息和建议接收器，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[实现接收器告知对象](implementing-an-advise-sink-object.md)。 
  

