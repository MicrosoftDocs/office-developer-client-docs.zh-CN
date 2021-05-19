---
title: HrOpenABEntryWithExchangeContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b640a5aa-4e36-4983-bf11-9428809e830b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 415d108f7fd9e84ba2a9090658bc0923550390f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434051"
---
# <a name="hropenabentrywithexchangecontext"></a>HrOpenABEntryWithExchangeContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用 **pEmsmdbUID** 标识Exchange通讯簿打开 **entryID。** 此函数的工作方式与[IAddrBook：:D etails](iaddrbook-details.md)类似，只不过使用此函数可确保使用预期的 Exchange 通讯簿提供程序打开[IAddrBook：：OpenEntry。](iaddrbook-openentry.md) 
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrDoABDetailsWithExchangeContext(
  LPMAPISESSION pmsess,
  const MAPIUID *pEmsmdbUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _pmsess_
  
> [in]登录的 **IMAPISession**。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]指向 **emsmdbUID** 的指针，标识包含 Exchange 通讯簿提供程序的 Exchange Service，此函数应该使用该提供程序在条目标识符上显示详细信息。 如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的行为类似于[IAddrBook：:D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID，则此函数的行为类似于 [IAddrBook：:D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指定的条目标识符的字节计数。 
    
 _lpEntryID_
  
>  [in]指向表示要打开的通讯簿条目的条目标识符的指针。 
    
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
    

