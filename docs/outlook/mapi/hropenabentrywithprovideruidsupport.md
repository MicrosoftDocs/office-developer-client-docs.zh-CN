---
title: HrOpenABEntryWithProviderUIDSupport
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1fafc810-7cf3-4c8c-bf21-055ae34da690
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da40e240b60fa42c48185600b74c6162a966e6f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409543"
---
# <a name="hropenabentrywithprovideruidsupport"></a>HrOpenABEntryWithProviderUIDSupport

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行与 [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md) 函数相同的函数，只不过 **HrOpenABEntryWithProviderUIDSupport** 函数使用给定的支持对象（而不是使用会话和通讯簿）打开条目。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithProviderUIDSupport(
  const MAPIUID *pEmsabpUID,
  LPMAPISUP lpSup,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _pEmsabpUID_
  
> [in]指向 _emsabpUID_ 参数的指针，该参数标识Exchange用于显示条目标识符详细信息的通讯簿提供程序。 如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的作用与[IAddrBook：:D etails 完全相同](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID，则此函数也与 [IAddrBook：:D etails 完全相同](iaddrbook-details.md)。
    
 _lpSup_
  
> 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指定的条目标识符的字节计数。 
    
 _lpEntryID_
  
> [in]指向表示要打开的通讯簿条目的条目标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识符 (IID) 用于访问打开条目的接口的 IID 标识符。 传递 NULL 将返回对象的标准接口。 对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md)，对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。 调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。 
    
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
    
 _lpulObjType_
  
> [out]指向打开的条目类型的指针。
    
 _lppUnk_
  
> [out]指向已打开条目的指针的指针。
    

