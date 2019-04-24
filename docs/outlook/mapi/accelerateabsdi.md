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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322125"
---
# <a name="accelerateabsdi"></a>ACCELERATEABSDI
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于在无模式通讯簿对话框中处理加速键的回调函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|定义的函数实现者:  <br/> |MAPI  <br/> |
|定义的函数调用者:  <br/> |客户端应用程序  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时用于将用户界面信息传递给函数的特定于实现的值。 在 Microsoft Windows 上运行的应用程序中, _ulUIParam_是对话框的父窗口句柄, 其类型为 HWND, 转换为**ULONG_PTR**。 如果值为零, 则表示没有父窗口。 
    
 _lpvmsg_
  
> 实时指向 Windows 消息的指针。
    
## <a name="return-value"></a>返回值

带有**ACCELERATEABSDI**原型的函数将返回 TRUE (如果它处理邮件)。 
  
## <a name="remarks"></a>注解

基于**ACCELERATEABSDI**原型的函数仅用于无模式对话框, 即, 仅当客户端应用程序已在[ADRPARM](adrparm.md)结构的_ulFlags_成员中设置了 DIALOG_SDI 标志时。 
  
无模式对话框共享客户端应用程序的 Windows 消息循环, 而不是拥有自己的循环。 控制消息循环的应用程序不知道对话框使用的快捷键, 因此它调用基于**ACCELERATEABSDI**的函数来测试加速器键 (如 CTRL + P) 以进行打印, 并对其进行操作。 
  
当客户端使用[IAddrBook:: address](iaddrbook-address.md)方法调用无模式通讯簿对话框时, 客户端的消息循环会调用基于**ACCELERATEABSDI**的函数。 当 MAPI 调用基于[DISMISSMODELESS](dismissmodeless.md)函数原型的函数时, 将终止此调用。 
  

