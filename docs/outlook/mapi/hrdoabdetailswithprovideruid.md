---
title: HrDoABDetailsWithProviderUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 27741887-8405-49ed-b080-613613faf91b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fada57c45602f0a0b07276034101fa23a7525f5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775154"
---
# <a name="hrdoabdetailswithprovideruid"></a>HrDoABDetailsWithProviderUID

  
  
**适用于**： Outlook 
  
确保**OpenEntry**方法打开的预期的 Exchange 通讯簿提供程序。 此函数工作方式与[IAddrBook::Details](iaddrbook-details.md)类似，但打开**entryID**使用由_pEmsabpUID_标识 Exchange 通讯簿。
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrDoABDetailsWithProviderUID(
  const MAPIUID   *pEmsabpUID,
  LPADRBOOK        pAddrBook,
  ULONG_PTR FAR *  lpulUIParam,
  LPFNDISMISS      lpfnDismiss,
  LPVOID           lpvDismissContext,
  ULONG            cbEntryID,
  LPENTRYID        lpEntryID,
  LPFNBUTTON       lpfButtonCallback,
  LPVOID           lpvButtonContext,
  LPSTR           lpszButtonText,
  ULONG            ulFlags
);
```

## <a name="parameters"></a>参数

 _pEmsabpUID_
  
> [in]指向_emsabpUID_标识 Exchange 通讯簿提供程序的此函数应使用要显示的项标识符的详细信息。 如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数和函数调用并且与[IAddrBook::Details](iaddrbook-details.md)完全一样。 如果此参数为 NULL 或零 MAPIUID，此函数的还行为与[IAddrBook::Details](iaddrbook-details.md)完全相同。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _lpulUIParam_
  
> [输出]对话框中的父窗口句柄。
    
 _lpfnDismiss_
  
> [in]一个指向基于**DISMISSMODELESS**原型或为空的一个函数指针。 此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。 MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫详细信息对话框中不再处于活动状态。 
    
 _lpvDismissContext_
  
> [in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。 此参数仅适用于无模式对话框中的版本通过_ulFlags_参数中包括**DIALOG_SDI**标志。 
    
 _cbEntryID_
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]一个指向代表打开的通讯簿条目的项标识符。
    
 _lpfButtonCallback_
  
> [in]基于**LPFNBUTTON**函数原型函数指针。 **LPFNBUTTON**函数将按钮添加到详细信息对话框。 
    
 _lpvButtonContext_
  
> [in]指向作为参数指定由_lpfButtonCallback_参数的函数使用的数据的指针。 
    
 _lpszButtonText_
  
> [in]指向一个字符串，包含要应用于添加按钮，文本是否可扩展该按钮的指针。 不需要的可扩展按钮时， _lpszButtonText_参数应为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。 可以设置以下标志： 
    
AB_TELL_DETAILS_CHANGE
  
> 指示详细信息返回 TRUE 是否进行了更改实际的地址;否则，详细信息将返回 FALSE。
    
DIALOG_MODAL
  
> 显示模式版本的通用的地址对话框。 此标志是与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
> 显示通用的地址对话框的无模式版本。 此标志是与 DIALOG_MODAL 互斥。
    
MAPI_UNICODE
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    

