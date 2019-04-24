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
ms.openlocfilehash: 804bd23a148b942fd4580d1e3465fc1f65ff5978
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357440"
---
# <a name="lpfnbutton"></a>LPFNBUTTON

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于在通讯簿对话框中激活可选按钮控件的 MAPI 调用的回调函数。 此按钮通常为 "**详细信息**" 按钮。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|定义的函数实现者:  <br/> |服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
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
  
> 实时此函数显示的任何对话框或窗口的父窗口的句柄。
    
 _lpvContext_
  
> 实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。 此值可以表示对客户端应用程序的重要性的地址。 通常, 对于 c + + 代码, _lpvContext_表示指向 c + + 对象的指针。 
    
 _cbEntryID_
  
> 实时由_lpSelection_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _lpSelection_
  
> 实时指向定义对话框中所选内容的条目标识符的指针。
    
 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

客户端应用程序调用基于**LPFNBUTTON**原型的回调函数, 以在 "详细信息" 对话框中定义按钮。 客户端在对[IAddrBook::D etails](iaddrbook-details.md)方法的调用中传递指向回调函数的指针。 
  
服务提供程序调用基于**LPFNBUTTON**原型的挂钩函数, 以在 "详细信息" 对话框中定义按钮。 提供程序在对[IMAPISupport::D etails](imapisupport-details.md)方法的调用中传递指向此挂接函数的指针。 
  
在这两种情况下, 当显示对话框且用户选择已定义的按钮时, MAPI 将调用**LPFNBUTTON**。 
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)

