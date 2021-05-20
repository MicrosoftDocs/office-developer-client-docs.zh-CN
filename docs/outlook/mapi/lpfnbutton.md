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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431510"
---
# <a name="lpfnbutton"></a>LPFNBUTTON

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义 MAPI 调用的回调函数，以激活通讯簿对话框中的可选按钮控件。 此按钮通常为"详细信息 **"** 按钮。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|定义的函数实现方：  <br/> |服务提供程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
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
  
> [in]此函数显示的任何对话框或窗口的父窗口的句柄。
    
 _lpvContext_
  
> [in]指向 MAPI 调用回调函数时传递给回调函数的任意值的指针。 此值可以表示对客户端应用程序有意义的地址。 通常，对于 C++ 代码  _，lpvContext_ 表示指向 C++ 对象的指针。 
    
 _cbEntryID_
  
> [in]  _lpSelection_ 参数指向的条目标识符的大小（以字节为单位）。 
    
 _lpSelection_
  
> [in]指向定义对话框中选定内容项的条目标识符的指针。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

客户端应用程序基于 **LPFNBUTTON** 原型调用回调函数，以定义详细信息对话框中的按钮。 客户端在调用 [IAddrBook：:D etails 方法时传递指向回调函数的](iaddrbook-details.md) 指针。 
  
服务提供商基于 **LPFNBUTTON** 原型调用挂钩函数，以定义详细信息对话框中的按钮。 提供程序在调用 [IMAPISupport：:D etails](imapisupport-details.md) 方法时传递指向此挂钩函数的指针。 
  
在这两种情况下，当对话框显示并且用户选择定义的按钮时，MAPI 调用 **LPFNBUTTON**。 
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)

