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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426777"
---
# <a name="imapisupportdetails"></a>IMAPISupport::Details

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框，其中显示有关特定通讯簿条目的详细信息。
  
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
  
> [out]指向返回对话框的父窗口的句柄的指针。
    
 _lpfnDismiss_
  
> [in]指向基于 [DISMISSMODELESS](dismissmodeless.md) 原型的函数的指针，或 NULL。 此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。 当用户关闭无模式地址对话框时，MAPI 将调用 **DISMISSMODELESS** 函数，以通知调用 **IMAPISupport：:D的** 客户端该对话框不再处于活动状态。 
    
 _lpvDismissContext_
  
> [in]指向要传递给 _lpfnDismiss_ 参数指向的 **DISMISSMODELESS** 函数的上下文信息的指针。 此参数仅在  _ulFlags_ 参数中包括 DIALOG_SDI 标志，仅适用于对话框的无模式版本。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向显示其详细信息的条目标识符的指针。
    
 _lpfButtonCallback_
  
> [in]指向基于 [LPFNBUTTON](lpfnbutton.md) 函数原型的函数的指针。 **LPFNBUTTON** 函数将按钮添加到详细信息对话框中。 
    
 _lpvButtonContext_
  
> [in]指向用作  _lpfButtonCallback_ 参数所指定函数的参数的数据的指针。 
    
 _lpszButtonText_
  
> [in]指向包含要应用于所添加按钮的文本的字符串的指针（如果该按钮是可扩展的）。 如果不需要可扩展按钮，则  _lpszButtonText_ 参数应为 NULL。 
    
 _ulFlags_
  
> [in]控制  _lpszButtonText_ 参数的文本类型的标志位掩码。 可以设置以下标志： 
    
DIALOG_MODAL
  
> 显示常用地址对话框的模式版本。 此标志与 DIALOG_SDI。
    
DIALOG_SDI
  
>  显示公用地址对话框的无模式版本。 此标志与 DIALOG_MODAL。 
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示通讯簿条目的详细信息对话框。
    
## <a name="remarks"></a>备注

为 **通讯簿提供程序支持对象:D IMAPISupport：:D etails** 方法。 通讯簿提供程序调用 **Details** 可显示一个对话框，该对话框提供有关通讯簿中特定条目的详细信息。 _lpfButtonCallback、lpvButtonContext_ 和 _lpszButtonText_ 参数可用于向对话框添加客户端定义的按钮。  单击按钮时，MAPI 将调用  _lpfButtonCallback_ 指向的回调函数，同时传递按钮的条目标识符和  _lpvButtonContext 中的数据_。 如果不需要可扩展按钮  _，lpszButtonText_ 应为 NULL。 
  
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[LPFNBUTTON](lpfnbutton.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

