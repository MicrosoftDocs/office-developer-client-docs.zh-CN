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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426679"
---
# <a name="hrdoabdetailswithprovideruid"></a>HrDoABDetailsWithProviderUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确保由预期的通讯簿提供程序打开 **OpenEntry** Exchange打开。 此函数的工作方式类似于 [IAddrBook：:D etails，](iaddrbook-details.md)但使用 _pEmsabpUID_ 标识的 Exchange 通讯簿打开 **entryID。**
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向标识通讯簿提供程序的 _emsabpUID_ 的指针Exchange此函数应该用于显示条目标识符上的详细信息。 如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的作用与[IAddrBook：:D etails 完全相同](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID，则此函数也与 [IAddrBook：:D etails 完全相同](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _lpulUIParam_
  
> [out]对话框的父窗口的句柄。
    
 _lpfnDismiss_
  
> [in]指向基于 **DISMISSMODELESS** 原型的函数的指针，或 NULL。 此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。 MAPI 在用户关闭无模式地址对话框时调用 **DISMISSMODELESS** 函数，并通知调用 Details 的客户端该对话框不再处于活动状态。 
    
 _lpvDismissContext_
  
> [in]指向要传递给 _lpfnDismiss_ 参数指向的 **DISMISSMODELESS** 函数的上下文信息的指针。 此参数仅在 _ulFlags_ 参数中包括 **DIALOG_SDI** 标志来应用于对话框的无模式版本。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指定的条目标识符的字节计数。 
    
 _lpEntryID_
  
> [in]指向表示要打开的通讯簿条目的条目标识符的指针。
    
 _lpfButtonCallback_
  
> [in]指向基于 **LPFNBUTTON** 函数原型的函数的指针。 **LPFNBUTTON** 函数将按钮添加到详细信息对话框中。 
    
 _lpvButtonContext_
  
> [in]指向用作  _lpfButtonCallback_ 参数所指定函数的参数的数据的指针。 
    
 _lpszButtonText_
  
> [in]指向包含要应用于所添加按钮的文本的字符串的指针（如果该按钮是可扩展的）。 当  _不需要可扩展按钮时，lpszButtonText_ 参数应为 NULL。 
    
 _ulFlags_
  
> [in]控制  _lpszButtonText_ 参数的文本类型的标志位掩码。 可以设置以下标志： 
    
AB_TELL_DETAILS_CHANGE
  
> 指示如果实际对地址进行了更改，Details 将返回 TRUE;否则，Details 将返回 FALSE。
    
DIALOG_MODAL
  
> 显示常用地址对话框的模式版本。 此标志与 DIALOG_SDI。
    
DIALOG_SDI
  
> 显示公用地址对话框的无模式版本。 此标志与 DIALOG_MODAL。
    
MAPI_UNICODE
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    

