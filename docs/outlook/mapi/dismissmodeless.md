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
ms.openlocfilehash: dd962515a85cb6a4b8661a0fd5294cea55cd6e96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339772"
---
# <a name="dismissmodeless"></a>DISMISSMODELESS

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义在其消除无模式通讯簿对话框时 MAPI 调用的回调函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|定义的函数实现者:  <br/> |客户端应用程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
```cpp
void (STDMETHODCALLTYPE DISMISSMODELESS)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时一个特定于实现的值, 通常用于将用户界面信息传递给函数。 例如, 在 Microsoft Windows 中, 此参数是对话框的父窗口句柄, 其类型为 HWND, 转换为**ULONG_PTR**。 如果值为零, 则表示没有父窗口。 
    
 _lpvContext_
  
> 实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。 此值可以表示对客户端应用程序的重要性的地址。 通常, 对于 c + + 代码, _lpvContext_是指向 c + + 对象实例的地址的指针。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>注解

当客户端应用程序调用无模式通讯簿对话框时, 它将在其 Windows 消息循环中包含对基于[ACCELERATEABSDI](accelerateabsdi.md)原型 (检查和处理加速键) 的函数的调用。 当对话框关闭时, MAPI 将调用基于**DISMISSMODELESS**的函数, 以便客户端应用程序将停止调用基于**ACCELERATEABSDI**的函数。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)

