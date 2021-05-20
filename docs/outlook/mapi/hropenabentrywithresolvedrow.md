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
ms.openlocfilehash: 2eb643e0002e2159e3197d66e021aba0bb8c126f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429906"
---
# <a name="hropenabentrywithresolvedrow"></a>HrOpenABEntryWithResolvedRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行与 [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) 相同的函数，只是它会自动从解析的行获取 **emsabpUID** 并打开 **entryID**。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向解析的行的指针，用于获取 **emsabpUID** 并打开 **entryID**。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指定的条目标识符的字节计数。 
    
 _lpEntryID_
  
>  [in]指向表示要打开的通讯簿条目的条目标识符的指针。 
    
 _lpInterface_
  
> [in]指向用于访问打开 (的) 接口的 IID 标识符的指针。 传递 NULL 将返回对象的标准接口。 对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是 [IDistList ： IMAPIContainer，](idistlistimapicontainer.md)对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。 调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> [in]控制条目打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_BEST_ACCESS
  
> 请求以允许的最大网络和客户端权限打开条目。 例如，如果客户端具有读取和写入权限，通讯簿提供程序将尝试打开具有读取和写入权限的条目。 客户端可以检索通过调用打开条目的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。 
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿来执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
MAPI_DEFERRED_ERRORS
  
> 允许在条目完全打开且可用之前成功调用，这意味着对条目的后续调用可能会返回错误。
    
MAPI_GAL_ONLY
  
> 仅使用 GAL 执行名称解析。 此标志仅受通讯簿Exchange支持。
    
MAPI_MODIFY
  
> 请求使用读取和写入权限打开条目。 由于默认情况下使用只读访问权限打开条目，因此客户端不应假定已授予读取和写入权限，MAPI_MODIFY权限。
    
MAPI_NO_CACHE
  
> 不使用脱机通讯簿执行名称解析。 此标志仅受通讯簿Exchange支持。
    
 _lpulObjType_
  
> [out]指向打开的条目类型的指针。
    
 _lppUnk_
  
> [out]指向已打开条目的指针的指针。
    

