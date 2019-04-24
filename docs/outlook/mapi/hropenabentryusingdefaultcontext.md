---
title: HrOpenABEntryUsingDefaultContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17cba69b-2b25-4b99-99d9-ec68fb8a35b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f60c4d3761694439d10b073fda5bc36443c13e43
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347822"
---
# <a name="hropenabentryusingdefaultcontext"></a>HrOpenABEntryUsingDefaultContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行与[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)相同的功能, 只是它使用旧版**emsmdbUID**作为_pEmsmdbUID_参数。 除非您无法为对[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)的调用获取正确的**emsmdbUID** , 否则请不要使用此函数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrOpenABEntryUsingDefaultContext(
  LPMAPISESSION pmsess,
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

 _pmsess_
  
> 实时登录的**IMAPISession**。 它不能为 NULL。
    
 _pAddrBook_
  
> 实时用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID_
  
> 实时由_lpEntryID_参数指定的条目标识符的字节数。 
    
 _lpEntryID_
  
>  实时指向表示要打开的通讯簿条目的条目标识符的指针。 
    
 _lpInterface_
  
> 实时指向用于访问打开项的接口的接口标识符 (IID) 的指针。 传递 NULL 将返回对象的标准接口。 对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md), 而对于容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> 实时用于控制条目打开方式的标志的位掩码。 可以设置以下标志:
    
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
  
> 不使用脱机通讯簿执行名称解析。 仅 Exchange 通讯簿提供程序支持此标志。
    
 _lpulObjType_
  
> 排除指向已打开条目的类型的指针。
    
 _lppUnk_
  
> 排除指向已打开条目的指针的指针。
    

