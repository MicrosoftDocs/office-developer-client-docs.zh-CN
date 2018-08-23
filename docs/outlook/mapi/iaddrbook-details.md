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
ms.openlocfilehash: e240ec4e7a61b9e7484f467926501f8c5f5a59f8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592344"
---
# <a name="iaddrbookdetails"></a>IAddrBook::Details

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]指向对话框中的父窗口的句柄的指针。
    
 _lpfnDismiss_
  
> [in]一个指向基于[DISMISSMODELESS](dismissmodeless.md)原型或为空的一个函数指针。 此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。 MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫**详细信息**对话框中不再处于活动状态。 
    
 _lpvDismissContext_
  
> [in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。 此参数仅适用于无模式版本的对话框中，通过_ulFlags_参数中包括 DIALOG_SDI 标志。 
    
 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要显示其详细信息的条目的项标识符的指针。
    
 _lpfButtonCallback_
  
> [in]基于[LPFNBUTTON](lpfnbutton.md)函数原型函数指针。 **LPFNBUTTON**函数将按钮添加到详细信息对话框。 
    
 _lpvButtonContext_
  
> [in]指向作为参数指定由_lpfButtonCallback_参数的函数使用的数据的指针。 
    
 _lpszButtonText_
  
> [in]指向一个字符串，包含要应用于添加按钮，文本是否可扩展该按钮的指针。 _LpszButtonText_参数应为 NULL，如果您不需要的可扩展的按钮。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。 可以设置以下标志： 
    
AB_TELL_DETAILS_CHANGE
  
> 指示的**详细信息**，则返回 S_OK 如果进行了更改实际的地址;否则，**详细信息**返回 S_FALSE。 
    
DIALOG_MODAL
  
> 显示通用的地址对话框，其中始终显示非 Outlook 客户端中的模式版本。 此标志是与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
>  显示通用的地址对话框的无模式版本。 非 Outlook 客户端，则忽略此标志。 
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功的通讯簿条目显示详细信息对话框。
    
## <a name="remarks"></a>注解

客户端应用程序调用以显示一个对话框，提供了有关在通讯簿中的特定条目的详细信息， **Details**方法。 _LpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数用于将客户端定义按钮添加到对话框。 单击按钮时，MAPI 调用的回调函数所指的_lpfButtonCallback_， _lpvButtonContext_中传递按钮和数据的项标识符。 如果您不需要的可扩展的按钮， _lpszButtonText_应为 NULL。 
  
 **详细信息**支持 Unicode 字符的字符串;Unicode 字符串转换为多字节字符的字符串 (MBCS) 格式显示在详细信息对话框之前。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog::OnOpenEntryID  <br/> |MFCMAPI 使用， **Details**方法显示一个对话框，显示的通讯簿条目的详细信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRPARM](adrparm.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[LPFNBUTTON](lpfnbutton.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

