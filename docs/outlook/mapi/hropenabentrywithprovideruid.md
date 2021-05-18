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
  
使用 _pEmsabpUID_ 标识Exchange通讯簿打开 entryID。 此函数的工作方式与[IAddrBook：：OpenEntry](iaddrbook-openentry.md)类似，只是使用此函数可确保使用预期的通讯簿提供程序打开[IAddrBook：：OpenEntry](iaddrbook-openentry.md) Exchange打开。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向 **emsmdbUID** 的指针，标识包含 Exchange 通讯簿提供程序的 Exchange Service，此函数应该使用该提供程序在条目标识符上显示详细信息。 如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的行为类似于[IAddrBook：:D etails](iaddrbook-details.md)。 如果此参数为 NULL 或零 MAPIUID，则此函数的行为类似于 [IAddrBook：:D etails](iaddrbook-details.md)。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指定的条目标识符的字节计数。 
    
 _lpEntryID_
  
>  [in]指向表示要打开的通讯簿条目的条目标识符的指针。 
    
 _lpInterface_
  
> [in]指向用于访问打开 (的) 接口的 IID 标识符的指针。 传递 NULL 将返回对象的标准接口。 对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是 [IDistList ： IMAPIContainer，](idistlistimapicontainer.md)对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。 调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。 
    
 _ulFlags_
  
> [in]控制条目打开方式的标志的位掩码，可以设置以下标志：
    
MAPI_BEST_ACCESS
  
> 请求以允许的最大网络和客户端权限打开条目。 例如，如果客户端具有读取和写入权限，通讯簿提供程序将尝试打开具有读取和写入权限的条目。 客户端可以检索通过调用打开条目的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。 
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
MAPI_DEFERRED_ERRORS
  
> 允许在条目完全打开且可用之前成功调用，这意味着对条目的后续调用可能会返回错误。
    
MAPI_GAL_ONLY
  
> 仅使用 GAL 执行名称解析。 此标志仅受通讯簿Exchange支持。
    
MAPI_MODIFY
  
> 请求使用读取和写入权限打开条目。 由于默认情况下使用只读访问权限打开条目，因此客户端不应假定已授予读取和写入权限，MAPI_MODIFY权限。
    
MAPI_NO_CACHE
  
> 请勿使用脱机通讯簿执行名称解析。 此标志仅受通讯簿Exchange支持。
    
 _lpulObjType_
  
> [out]指向打开的条目类型的指针。
    
 _lppUnk_
  
> [out]指向已打开条目的指针的指针。
    

