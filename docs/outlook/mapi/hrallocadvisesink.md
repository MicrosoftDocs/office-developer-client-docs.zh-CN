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
ms.openlocfilehash: 5a5e736e8be1120f5fb90048f01fdc8a44479060
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775141"
---
# <a name="hrallocadvisesink"></a>HrAllocAdviseSink

  
  
**适用于**： Outlook 
  
创建 advise 接收器对象，由指定的呼叫的实现，回调函数以触发的事件通知的上下文。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
STDAPI HrAllocAdviseSink(
  LPNOTIFCALLBACK lpfnCallback,
  LPVOID lpvContext,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a>参数

 _lpfnCallback_
  
> [in]指向[NOTIFCALLBACK](notifcallback.md)原型的 MAPI 调用的新创建的通知事件发生时所基于的回调函数建议接收器。 
    
 _lpvContext_
  
> [in]MAPI 调用它时，呼叫者数据的指针传递给回调函数。 呼叫者数据可以表示为客户端或提供程序的有效位倍数的地址。 通常情况下，c + + 代码_lpvContext_参数为地址的对象表示的指针。 
    
 _lppAdviseSink_
  
> [输出]指向 advise 接收器对象的指针的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

若要使用**HrAllocAdviseSink**函数，客户端应用程序或服务提供商创建一个对象，以接收通知，创建基于[NOTIFCALLBACK](notifcallback.md)函数原型对象，该对象与对应的通知回调函数和一个指针传递给作为_lpvContext_值的**HrAllocAdviseSink**函数中的对象。 这样执行通知;并作为通知过程的一部分，MAPI 调用的回调函数与作为上下文的对象指针。 
  
MAPI 异步实现其通知引擎。 在 c + +，通知回调可以是对象的方法。 如果生成通知的对象不存在，客户端或提供程序请求通知必须保留的对象的对象的单独引用计数建议接收器。 
  
> [!CAUTION]
> 应谨慎; 使用**HrAllocAdviseSink**它是为客户端创建自己的 advise 接收器更安全。 
  

