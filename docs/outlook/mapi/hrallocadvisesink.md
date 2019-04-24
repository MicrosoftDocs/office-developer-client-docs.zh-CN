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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348214"
---
# <a name="hrallocadvisesink"></a>HrAllocAdviseSink

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在给定调用实现指定的上下文和事件通知触发的回调函数的情况下, 创建一个建议接收器对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
STDAPI HrAllocAdviseSink(
  LPNOTIFCALLBACK lpfnCallback,
  LPVOID lpvContext,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a>参数

 _lpfnCallback_
  
> 实时指向基于[NOTIFCALLBACK](notifcallback.md)原型的回调函数的指针, 新创建的通知接收器的通知事件发生时, MAPI 将调用此函数。 
    
 _lpvContext_
  
> 实时指向在 MAPI 调用回调函数时传递给该函数的调用方数据的指针。 呼叫者数据可以表示对客户端或提供程序的重要性的地址。 通常, 对于 c + + 代码, _lpvContext_参数表示指向对象地址的指针。 
    
 _lppAdviseSink_
  
> 排除指向建议接收器对象的指针的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

若要使用**HrAllocAdviseSink**函数, 客户端应用程序或服务提供程序将创建一个用于接收通知的对象, 基于与该对象一起使用的[NOTIFCALLBACK](notifcallback.md)函数原型创建一个通知回调函数。并将指向**HrAllocAdviseSink**函数中的对象的指针作为_lpvContext_值传递。 执行此操作将执行通知;作为通知过程的一部分, MAPI 将调用回调函数, 并将对象指针作为上下文。 
  
MAPI 以异步方式实现其通知引擎。 在 c + + 中, 通知回调可以是对象方法。 如果生成通知的对象不存在, 则请求通知的客户端或提供程序必须为该对象的通知接收器保留一个单独的引用计数。 
  
> [!CAUTION]
> 应谨慎使用**HrAllocAdviseSink** ;客户端更安全地创建自己的建议接收器。 
  

