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
ms.openlocfilehash: b7d4d758f7031c55aa3a23b662ec8727ea1e0719
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774493"
---
# <a name="accelerateabsdi"></a>ACCELERATEABSDI
 
**适用于**： Outlook 
  
定义为无模式的通讯簿对话框中的过程加速键的回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实施定义的函数：  <br/> |MAPI  <br/> |
|定义的函数调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]用于将用户界面的信息传递给函数的特定于实现的值。 在 Microsoft Windows 上运行的应用程序， _ulUIParam_是对话框中的父窗口句柄，并且是类型 HWND，强制转换为**ULONG_PTR**。 值为零表示没有父窗口。 
    
 _lpvmsg_
  
> [in]为 Windows 的消息的指针。
    
## <a name="return-value"></a>返回值

如果它处理的消息，带有**ACCELERATEABSDI**原型的函数将返回 TRUE。 
  
## <a name="remarks"></a>说明

基于**ACCELERATEABSDI**原型函数仅用于无模式对话框，即，只有当客户端应用程序已在[ADRPARM](adrparm.md)结构的_ulFlags_成员设置 DIALOG_SDI 标志。 
  
无模式对话框共享客户端应用程序的 Windows 消息循环，而不是让其自己的循环。 该应用程序，用于控制消息循环，不知道哪些对话框用法，因此它将调用**ACCELERATEABSDI**将函数测试和处理基于快捷键 CTRL + P 如打印的加速键。 
  
在客户端使用[IAddrBook::Address](iaddrbook-address.md)方法调用无模式的通讯簿对话框时，客户端的消息循环调用**ACCELERATEABSDI**基于函数。 MAPI 调用基于[DISMISSMODELESS](dismissmodeless.md)函数原型函数时，将终止此呼叫。 
  

