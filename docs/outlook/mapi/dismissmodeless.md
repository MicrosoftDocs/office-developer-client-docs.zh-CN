---
title: DISMISSMODELESS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DISMISSMODELESS
api_type:
- COM
ms.assetid: ef93ef3d-c159-40ae-9b8d-0af8a0567565
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c66ff2338eb5751dbffe392a6a26258fb1c89476
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565835"
---
# <a name="dismissmodeless"></a>DISMISSMODELESS

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
定义一个时它解除了无模式的通讯簿对话框 MAPI 调用的回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实施定义的函数：  <br/> |客户端应用程序  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
void (STDMETHODCALLTYPE DISMISSMODELESS)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]通常用于将用户界面的信息传递给函数的特定于实现的值。 例如，Microsoft Windows 中此参数是对话框中的父窗口句柄的类型 HWND，强制转换为**ULONG_PTR**。 值为零表示没有父窗口。 
    
 _lpvContext_
  
> [in]MAPI 调用它时，为任意值的指针传递给回调函数。 此值可表示的客户端应用程序的有效位倍数的地址。 通常，c + + 代码_lpvContext_是一个指向 c + + 对象实例的地址。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>注解

当客户端应用程序调用无模式的通讯簿对话框时，它在其 Windows 消息循环中包括对基于[ACCELERATEABSDI](accelerateabsdi.md)原型，其检查和处理快捷键函数的调用。 当关闭对话框时，MAPI 调用**DISMISSMODELESS**基于函数，以便客户端应用程序将停止调用**ACCELERATEABSDI**基于函数。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)

