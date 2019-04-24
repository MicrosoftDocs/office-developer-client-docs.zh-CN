---
title: IMAPISupportDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Details
api_type:
- COM
ms.assetid: 1a62efa2-dd6b-4acb-a760-defa601c20c9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bdc57a6e951e54640fe3c638977c6a5f16986e68
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322356"
---
# <a name="imapisupportdetails"></a>IMAPISupport::Details

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框, 显示有关特定通讯簿条目的详细信息。
  
```cpp
HRESULT Details(
  ULONG_PTR FAR * lpulUIParam,
  LPFNDISMISS lpfnDismiss,
  LPVOID lpvDismissContext,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPFNBUTTON lpfButtonCallback,
  LPVOID lpvButtonContext,
  LPSTR lpszButtonText,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> 排除指向返回的对话框的父窗口的句柄的指针。
    
 _lpfnDismiss_
  
> 实时指向基于[DISMISSMODELESS](dismissmodeless.md)原型的函数的指针或 NULL。 此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。 MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 通知客户端正在调用**IMAPISupport::D etails**该对话框不再处于活动状态。 
    
 _lpvDismissContext_
  
> 实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。 此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含 DIALOG_SDI 标志。 
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向显示其详细信息的条目标识符的指针。
    
 _lpfButtonCallback_
  
> 实时指向基于[LPFNBUTTON](lpfnbutton.md)函数原型的函数的指针。 **LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。 
    
 _lpvButtonContext_
  
> 实时指向用作参数的数据的指针, 该函数由_lpfButtonCallback_参数指定。 
    
 _lpszButtonText_
  
> 实时指向包含要应用于已添加按钮的文本的字符串的指针 (如果该按钮是可扩展的)。 如果不需要可扩展按钮, 则_lpszButtonText_参数应为 NULL。 
    
 _ulFlags_
  
> 实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。 可以设置以下标志: 
    
DIALOG_MODAL
  
> 显示 "常用地址" 对话框的 "模式" 版本。 此标志与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
>  显示 "常用地址" 对话框的无模式版本。 此标志与 DIALOG_MODAL 互斥。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示通讯簿条目的 "详细信息" 对话框。
    
## <a name="remarks"></a>注解

**IMAPISupport::D etails**方法是为通讯簿提供程序支持对象而实现的。 通讯簿提供程序调用**详细信息**以显示一个对话框, 该对话框提供有关通讯簿中的特定条目的详细信息。 _lpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数可用于将客户端定义的按钮添加到对话框中。 单击该按钮时, MAPI 将调用_lpfButtonCallback_指向的回调函数, 同时传递按钮的条目标识符和_lpvButtonContext_中的数据。 如果不需要可扩展按钮, _lpszButtonText_应为 NULL。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[LPFNBUTTON](lpfnbutton.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

