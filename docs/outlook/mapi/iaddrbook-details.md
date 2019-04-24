---
title: IAddrBookDetails
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Details
api_type:
- COM
ms.assetid: 4eee4382-98c3-4714-8920-8d72edef00b8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5fbd20a6b5d5598b8fa51f9c369eefac9a1ea2e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341718"
---
# <a name="iaddrbookdetails"></a>IAddrBook::Details

  
  
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
  
> 实时指向对话框父窗口的句柄的指针。
    
 _lpfnDismiss_
  
> 实时指向基于[DISMISSMODELESS](dismissmodeless.md)原型的函数的指针或 NULL。 此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。 MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 告知客户端正在调用对话框中不再处于活动状态的**详细信息**。 
    
 _lpvDismissContext_
  
> 实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。 此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含 DIALOG_SDI 标志。 
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向显示其详细信息的条目的条目标识符的指针。
    
 _lpfButtonCallback_
  
> 实时指向基于[LPFNBUTTON](lpfnbutton.md)函数原型的函数的指针。 **LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。 
    
 _lpvButtonContext_
  
> 实时指向用作_lpfButtonCallback_参数所指定函数的参数的数据的指针。 
    
 _lpszButtonText_
  
> 实时指向一个字符串的指针, 该字符串包含要应用于已添加按钮的文本 (如果该按钮是可扩展的)。 如果不需要可扩展按钮, 则_lpszButtonText_参数应为 NULL。 
    
 _ulFlags_
  
> 实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。 可以设置以下标志: 
    
AB_TELL_DETAILS_CHANGE
  
> 指示如果实际对地址进行了更改, 则**详细信息**返回 S_OK; 否则返回 false。否则,**详细信息**将返回 S_FALSE。 
    
DIALOG_MODAL
  
> 显示 "常用地址" 对话框的模式版本, 该对话框始终显示在非 Outlook 客户端中。 此标志与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
>  显示 "常用地址" 对话框的无模式版本。 对于非 Outlook 客户端, 此标志将被忽略。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示通讯簿条目的 "详细信息" 对话框。
    
## <a name="remarks"></a>注解

客户端应用程序调用**详细信息**方法以显示一个对话框, 该对话框提供有关通讯簿中的特定条目的详细信息。 您可以使用_lpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数将客户端定义的按钮添加到对话框中。 单击该按钮时, MAPI 将调用_lpfButtonCallback_指向的回调函数, 同时传递按钮的条目标识符和_lpvButtonContext_中的数据。 如果不需要可扩展按钮, _lpszButtonText_应为 NULL。 
  
 **详细信息**支持 Unicode 字符字符串;在将 Unicode 字符串显示在 "详细信息" 对话框中之前, 它们将转换为多字节字符字符串 (MBCS) 格式。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog  <br/> |CBaseDialog:: OnOpenEntryID  <br/> |MFCMAPI 使用**详细信息**方法显示一个对话框, 其中显示了通讯簿条目的详细信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[LPFNBUTTON](lpfnbutton.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

