---
title: ACCELERATEABSDI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ACCELERATEABSDI
api_type:
- HeaderDef
ms.assetid: da67dcf4-1411-4fc9-992c-115485019bd3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 46e87caa68a45a188272340db408c52546f02a57
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420372"
---
# <a name="accelerateabsdi"></a>ACCELERATEABSDI
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义回调函数以在无模式通讯簿对话框中处理加速键。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|定义的函数实现方：  <br/> |MAPI  <br/> |
|由调用的已定义函数：  <br/> |客户端应用程序  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]用于将用户界面信息传递给函数的特定于实现的值。 在 Microsoft Windows 上运行的应用程序中 _，ulUIParam_ 是对话框的父窗口句柄，并且类型为 HWND，请强制转换到ULONG_PTR **。** 值为零表示没有父窗口。 
    
 _lpvmsg_
  
> [in]指向邮件Windows指针。
    
## <a name="return-value"></a>返回值

如果具有 **ACCELERATEABSDI** 原型的函数处理消息，则返回 TRUE。 
  
## <a name="remarks"></a>备注

基于 **ACCELERATEABSDI** 原型的函数仅用于无模式对话框，即，只有当客户端应用程序在 [ADRPARM](adrparm.md)结构的 _ulFlags_ 成员中设置了 DIALOG_SDI 标志时。 
  
无模式对话框共享客户端应用程序的Windows消息循环，而不是有自己的循环。 应用程序控制消息循环，它不知道对话框使用哪些加速键，因此它调用基于 **ACCELERATEABSDI** 的函数来测试加速键（如 Ctrl+P）并针对打印操作。 
  
当客户端使用 [IAddrBook：：Address](iaddrbook-address.md)方法调用无模式通讯簿对话框时，客户端的邮件循环将调用基于 **ACCELERATEABSDI** 的函数。 当 MAPI 调用基于 [DISMISSMODELESS](dismissmodeless.md) 函数原型的函数时，此调用将终止。 
  

