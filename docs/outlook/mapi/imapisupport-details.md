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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9923813d821e2b34497e3b498c19ce22ceda2eb0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775597"
---
# <a name="imapisupportdetails"></a>IMAPISupport::Details

  
  
**适用于**： Outlook 
  
显示一个对话框，显示有关特定通讯簿条目的详细信息。
  
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
  
> [输出]指向返回对话框的父窗口的句柄的指针。
    
 _lpfnDismiss_
  
> [in]一个指向基于[DISMISSMODELESS](dismissmodeless.md)原型或为空的一个函数指针。 此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。 MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫**IMAPISupport::Details**对话框中不再处于活动状态。 
    
 _lpvDismissContext_
  
> [in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。 此参数仅适用于无模式版本的对话框中，通过_ulFlags_参数中包括 DIALOG_SDI 标志。 
    
 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要显示其详细信息的项标识符的指针。
    
 _lpfButtonCallback_
  
> [in]基于[LPFNBUTTON](lpfnbutton.md)函数原型函数指针。 **LPFNBUTTON**函数将按钮添加到详细信息对话框。 
    
 _lpvButtonContext_
  
> [in]指向作为参数用于指定_lpfButtonCallback_参数的函数的数据的指针。 
    
 _lpszButtonText_
  
> [in]一个指向一个字符串，包含文本可扩展该按钮时要应用于添加按钮。 _LpszButtonText_参数应为 NULL，如果不需要的可扩展的按钮。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。 可以设置以下标记： 
    
DIALOG_MODAL
  
> 显示通用的地址对话框的模式版本。 此标志是与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
>  显示通用的地址对话框的无模式版本。 此标志是与 DIALOG_MODAL 互斥。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功的通讯簿条目显示详细信息对话框。
    
## <a name="remarks"></a>说明

对于通讯簿提供程序支持对象实现**IMAPISupport::Details**方法。 通讯簿提供程序呼叫**详细信息**，以显示一个对话框，提供有关在通讯簿中的特定条目详细信息。 _LpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数可用于将客户端定义按钮添加到对话框。 单击按钮时，MAPI 调用的回调函数所指的_lpfButtonCallback_， _lpvButtonContext_中传递按钮和数据的项标识符。 如果不需要的可扩展的按钮， _lpszButtonText_应为 NULL。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[LPFNBUTTON](lpfnbutton.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

