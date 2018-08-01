---
title: LPFNBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LPFNBUTTON
api_type:
- COM
ms.assetid: cb91ae1d-1ea8-4f02-a1f1-f2a356a71477
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1f15a5f031f5c5a9568b8a36722eaac011b814c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776148"
---
# <a name="lpfnbutton"></a>LPFNBUTTON

  
  
**适用于**： Outlook 
  
定义一个 MAPI 调用激活通讯簿对话框中的一个可选的按钮控件的回调函数。 此按钮通常是一个**详细信息**按钮。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实施定义的函数：  <br/> |服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
SCODE (STDMETHODCALLTYPE FAR * LPFNBUTTON)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext,
  ULONG cbEntryID,
  LPENTRYID lpSelection,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]任何对话框的父窗口或该函数将显示的窗口的句柄。
    
 _lpvContext_
  
> [in]MAPI 调用它时，为任意值的指针传递给回调函数。 此值可表示的客户端应用程序的有效位倍数的地址。 通常，c + + 代码_lpvContext_对 c + + 对象表示的指针。 
    
 _cbEntryID_
  
> [in]大小，以字节为单位_lpSelection_参数指向的项标识符。 
    
 _lpSelection_
  
> [in]在对话框中定义所选内容的项标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

客户端应用程序调用基于**LPFNBUTTON**原型，用于定义按钮，在详细信息对话框的回调函数。 客户端将指针传递给回调函数中调用[IAddrBook::Details](iaddrbook-details.md)方法。 
  
服务提供商调用挂接函数基于**LPFNBUTTON**原型，用于定义在详细信息对话框中的按钮。 提供程序将指针传递给此挂接函数中调用[IMAPISupport::Details](imapisupport-details.md)方法。 
  
在这两种情况下，当显示对话框，用户选择定义按钮，MAPI 调用**LPFNBUTTON**。 
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)

