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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428184"
---
# <a name="dismissmodeless"></a>DISMISSMODELESS

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义 MAPI 在消除无模式通讯簿对话框时调用的回调函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|定义的函数实现方：  <br/> |客户端应用程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
```cpp
void (STDMETHODCALLTYPE DISMISSMODELESS)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]一个特定于实现的值，通常用于将用户界面信息传递给函数。 例如，在 Microsoft Windows此参数是对话框的父窗口句柄，并且类型为 HWND，请强制转换到 ULONG_PTR **。** 值为零表示没有父窗口。 
    
 _lpvContext_
  
> [in]指向 MAPI 调用回调函数时传递给回调函数的任意值的指针。 此值可以表示对客户端应用程序有意义的地址。 通常，对于 C++ 代码  _，lpvContext_ 是指向 C++ 对象实例地址的指针。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>备注

当客户端应用程序调用无模式通讯簿对话框时，它会在其 Windows 消息中包含对基于[ACCELERATEABSDI](accelerateabsdi.md)原型的函数的调用，该原型将检查并处理加速键。 关闭对话框时，MAPI 将调用基于 **DISMISSMODELESS** 的函数，以便客户端应用程序停止调用 **基于 ACCELERATEABSDI** 的函数。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)

