---
title: HrAllocAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrAllocAdviseSink
api_type:
- HeaderDef
ms.assetid: 1dd460e6-ce95-4fef-bb5e-8d778c9716d5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f9873fe8e1825c68d4540cc1d093171e9f95727
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428898"
---
# <a name="hrallocadvisesink"></a>HrAllocAdviseSink

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在给定由调用实现指定的上下文和要由事件通知触发的回调函数的情况下，创建建议接收对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
STDAPI HrAllocAdviseSink(
  LPNOTIFCALLBACK lpfnCallback,
  LPVOID lpvContext,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a>参数

 _lpfnCallback_
  
> [in]指向基于 [NOTIFCALLBACK](notifcallback.md) 原型的回调函数的指针，MAPI 在针对新创建的通知接收器发生通知事件时将调用该原型。 
    
 _lpvContext_
  
> [in]指向在 MAPI 调用回调函数时传递给回调函数的调用方数据的指针。 呼叫者数据可以表示对客户端或提供程序有意义的地址。 通常，对于 C++ 代码  _，lpvContext_ 参数表示指向对象地址的指针。 
    
 _lppAdviseSink_
  
> [out]指向建议接收对象的指针的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

若要使用 **HrAllocAdviseSink** 函数，客户端应用程序或服务提供商会创建一个对象以接收通知，基于随该对象一起发送的 [NOTIFCALLBACK](notifcallback.md) 函数原型创建通知回调函数，将指向 **HrAllocAdviseSink** 函数中的对象的指针作为  _lpvContext_ 值传递。 执行此操作将执行通知;作为通知过程的一部分，MAPI 将对象指针作为上下文调用回调函数。 
  
MAPI 异步实现其通知引擎。 在 C++ 中，通知回调可以是对象方法。 如果生成通知的对象不存在，则请求通知的客户端或提供程序必须针对对象的通知接收器为该对象保留单独的引用计数。 
  
> [!CAUTION]
> **应谨慎使用 HrAllocAdviseSink;** 客户端创建自己的建议接收器会更安全。 
  

