---
title: HrOpenABEntryWithResolvedRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ce3a583c-16a9-4268-9476-926d2780eae5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9572f44f1f4865fcce5d7aa8bd8478340b0de968
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594717"
---
# <a name="hropenabentrywithresolvedrow"></a>HrOpenABEntryWithResolvedRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在于它会自动从解决的行中获取**emsabpUID**和打开**entryID**执行[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)相同的功能。
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithResolvedRow(
  LPSRow prwResolved,
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

 _prwResolved_
  
> [in]一个指向用于获取**emsabpUID**和打开**entryID**解决的行。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
>  [in]一个指向代表打开的通讯簿条目的项标识符。 
    
 _lpInterface_
  
> [in]指向用于访问打开条目的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回标准接口的对象。 对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开该条目。 可以设置以下标志：
    
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
    

