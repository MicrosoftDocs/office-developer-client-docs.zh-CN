---
title: HrOpenABEntryWithProviderUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 83821a86-abff-460c-bb8e-9fd9d232dc6b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20344185ffcbd90017fa3c3493218bd9b3ddfd74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408892"
---
# <a name="hropenabentrywithprovideruid"></a>HrOpenABEntryWithProviderUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用由_pEmsabpUID_标识的 Exchange 通讯簿打开**entryID** 。 此函数的工作方式类似于[IAddrBook:: OpenEntry](iaddrbook-openentry.md) , 只是使用此函数可确保使用预期的 Exchange 通讯簿提供程序打开[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithProviderUID(
  const MAPIUID *pEmsabpUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _pEmsmdbUID_
  
> 实时指向**emsmdbUID**的指针, 该链接标识包含此函数应用于显示条目标识符详细信息的 exchange 通讯簿提供程序的 exchange 服务。 如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数调用的行为就像[IAddrBook::D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID, 则此函数的行为类似于[IAddrBook::D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> 实时用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指定的条目标识符的字节数。 
    
 _lpEntryID_
  
>  实时指向表示要打开的通讯簿条目的条目标识符的指针。 
    
 _lpInterface_
  
> 实时指向用于访问打开项的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回对象的标准接口。 对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)和容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> 实时标志的位掩码, 可控制项的打开方式, 可以设置以下标志:
    
MAPI_BEST_ACCESS
  
> 请求使用最大允许的网络和客户端权限打开条目。 例如, 如果客户端具有读取和写入权限, 则通讯簿提供程序将尝试打开具有读取和写入权限的条目。 客户端可以通过调用 open 项的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性来检索已授予的访问级别。 
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。
    
MAPI_DEFERRED_ERRORS
  
> 允许调用成功 (可能在条目完全打开且可用之前), 这意味着随后对该条目的调用可能会返回错误。
    
MAPI_GAL_ONLY
  
> 仅使用 GAL 执行名称解析。 仅 Exchange 通讯簿提供程序支持此标志。
    
MAPI_MODIFY
  
> 请求使用 "读取" 和 "写入" 权限打开条目。 由于默认情况下会打开具有只读访问权限的条目, 因此客户端不应假定已授予 "读取" 和 "写入" 权限, 而不管是否设置了 MAPI_MODIFY。
    
MAPI_NO_CACHE
  
> 请勿使用脱机通讯簿执行名称解析。 仅 Exchange 通讯簿提供程序支持此标志。
    
 _lpulObjType_
  
> 排除指向已打开条目的类型的指针。
    
 _lppUnk_
  
> 排除指向已打开条目的指针的指针。
    

