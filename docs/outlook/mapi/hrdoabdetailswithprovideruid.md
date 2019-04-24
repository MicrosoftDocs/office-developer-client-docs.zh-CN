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
ms.openlocfilehash: 47cf87fce0af3b866018bf03a34a05ea42cef82c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347843"
---
# <a name="hrdoabdetailswithprovideruid"></a>HrDoABDetailsWithProviderUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确保**OpenEntry**方法由预期的 Exchange 通讯簿提供程序打开。 此函数的工作方式类似于[IAddrBook::D etails](iaddrbook-details.md) , 但使用_pEmsabpUID_标识的 Exchange 通讯簿打开**entryID** 。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时一个指向标识 Exchange 通讯簿提供程序的_emsabpUID_的指针。该函数应使用它来显示有关条目标识符的详细信息。 如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数调用的行为完全像[IAddrBook::D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID, 则此函数也相当于[IAddrBook::D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> 实时用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _lpulUIParam_
  
> 排除对话框的父窗口的句柄。
    
 _lpfnDismiss_
  
> 实时指向基于**DISMISSMODELESS**原型的函数的指针或 NULL。 此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。 MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 告知客户端正在调用对话框中不再处于活动状态的详细信息。 
    
 _lpvDismissContext_
  
> 实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。 此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含**DIALOG_SDI**标志。 
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指定的条目标识符的字节数。 
    
 _lpEntryID_
  
> 实时指向表示要打开的通讯簿条目的条目标识符的指针。
    
 _lpfButtonCallback_
  
> 实时指向基于**LPFNBUTTON**函数原型的函数的指针。 **LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。 
    
 _lpvButtonContext_
  
> 实时指向用作_lpfButtonCallback_参数所指定函数的参数的数据的指针。 
    
 _lpszButtonText_
  
> 实时指向一个字符串的指针, 该字符串包含要应用于已添加按钮的文本 (如果该按钮是可扩展的)。 当不需要可扩展按钮时, _lpszButtonText_参数应为 NULL。 
    
 _ulFlags_
  
> 实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。 可以设置以下标志: 
    
AB_TELL_DETAILS_CHANGE
  
> 指示如果实际对地址进行了更改, 则详细信息返回 TRUE; 否则返回 false。否则, 详细信息将返回 FALSE。
    
DIALOG_MODAL
  
> 显示 "常用地址" 对话框的模式版本。 此标志与 DIALOG_SDI 互斥。
    
DIALOG_SDI
  
> 显示 "常用地址" 对话框的无模式版本。 此标志与 DIALOG_MODAL 互斥。
    
MAPI_UNICODE
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    

