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
ms.openlocfilehash: e0b6718345588e79a8038f7cb409ef901d7c11f5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577154"
---
# <a name="hropenabentrywithexchangecontext"></a>HrOpenABEntryWithExchangeContext

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开使用由**pEmsmdbUID**标识 Exchange 通讯簿**entryID** 。 此功能向[IAddrBook::Details](iaddrbook-details.md)有效同样，只不过使用此函数可确保[IAddrBook::OpenEntry](iaddrbook-openentry.md)通过使用预期的 Exchange 通讯簿提供程序打开。 
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]登录**IMAPISession**。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]指向标识包含 Exchange 通讯簿提供程序，此函数应该使用要显示的项标识符的详细信息的 Exchange 服务**emsmdbUID**的指针。 如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数调用与[IAddrBook::Details](iaddrbook-details.md)相似之处。 如果此参数为 NULL 或零 MAPIUID，此函数的行为类似[IAddrBook::Details](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]_LpEntryID_参数指定的项标识符的字节数。 
    
 _lpEntryID_
  
>  [in]一个指向代表打开的通讯簿条目的项标识符。 
    
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
    

