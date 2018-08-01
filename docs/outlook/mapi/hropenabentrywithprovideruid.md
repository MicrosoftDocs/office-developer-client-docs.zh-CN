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
ms.openlocfilehash: e33e656e70802437ab8b8717c5e175e2a13e384e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775172"
---
# <a name="hropenabentrywithprovideruid"></a>HrOpenABEntryWithProviderUID

  
  
**适用于**： Outlook 
  
打开使用由_pEmsabpUID_标识 Exchange 通讯簿**entryID** 。 此功能向[IAddrBook::OpenEntry](iaddrbook-openentry.md)有效同样，只不过使用此函数可确保[IAddrBook::OpenEntry](iaddrbook-openentry.md)通过使用预期的 Exchange 通讯簿提供程序打开。 
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向标识包含 Exchange 通讯簿提供程序，此函数应该使用要显示的项标识符的详细信息的 Exchange 服务**emsmdbUID**的指针。 如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数调用与[IAddrBook::Details](iaddrbook-details.md)相似之处。 如果此参数为 NULL 或零 MAPIUID，此函数的行为类似[IAddrBook::Details](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
>  [in]一个指向代表打开的通讯簿条目的项标识符。 
    
 _lpInterface_
  
> [in]指向用于访问打开条目的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回标准接口的对象。 对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> [in]一个位掩码的标志，控制如何打开条目，可以设置以下标志：
    
MAPI_BEST_ACCESS
  
> 与最大允许网络和客户端权限打开的条目的请求。 例如，如果客户端具有读取和写入权限，通讯簿提供程序尝试打开条目具有读取和写入权限。 客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。 
    
MAPI_CACHE_ONLY
  
> 使用仅脱机通讯簿执行名称解析。 例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_DEFERRED_ERRORS
  
> 允许的调用成功，可能之前该条目是完全打开且可用，这意味着该条目的后面对会返回一个错误。
    
MAPI_GAL_ONLY
  
> 使用仅 GAL 执行名称解析。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_MODIFY
  
> 请求项打开的读取和写入权限。 因为条目具有只读访问权限打开默认情况下，客户端不应假定的读取和写入无论是否设置 MAPI_MODIFY 授予了权限。
    
MAPI_NO_CACHE
  
> 不使用脱机通讯簿执行名称解析。 此标志仅受 Exchange 通讯簿提供程序支持。
    
 _lpulObjType_
  
> [输出]一个指向打开条目的类型。
    
 _lppUnk_
  
> [输出]指向打开的条目的指针的指针。
    

