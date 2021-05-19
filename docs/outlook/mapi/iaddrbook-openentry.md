---
title: IAddrBookOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.OpenEntry
api_type:
- COM
ms.assetid: bd7746f4-8070-4cc5-8b8e-c527c5847545
description: 上次修改时间：2013 年 2 月 1 日
ms.openlocfilehash: 293fe5a65c760f61ab0073e0eafc1a606c69050f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434163"
---
# <a name="iaddrbookopenentry"></a>IAddrBook::OpenEntry

**适用于**：Outlook 2013 | Outlook 2016 
  
打开通讯簿条目，并返回一个指向可用于访问该条目的接口的指针。
  
```cpp
HRESULT OpenEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

_cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
_lpEntryID_
  
> [in]指向表示要打开的通讯簿条目的条目标识符的指针。
    
_lpInterface_
  
> [in]指向接口标识符 (IID) 用于访问打开条目的接口的 IID 标识符。 传递 NULL 将返回对象的标准接口。 对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是 [IDistList ： IMAPIContainer，](idistlistimapicontainer.md) 对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。 调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。 
    
_ulFlags_
  
> [in]控制条目打开方式的标志的位掩码。 可以设置以下标志。
    
MAPI_BEST_ACCESS 
  
> 请求以允许的最大网络和客户端权限打开条目。 例如，如果客户端具有读/写权限，通讯簿提供程序应尝试打开具有读/写权限的条目。 客户端可以通过调用打开条目的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法并检索 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性来检索授予的访问级别。
    
MAPI_CACHE_ONLY
  
> 打开通讯簿条目，并仅从缓存中访问该条目。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 只有通讯簿提供商才支持Exchange标志。
    
MAPI_DEFERRED_ERRORS 
  
> 允许调用成功，可能在条目完全打开且可用之前，这意味着稍后对条目的调用可能会返回错误。
    
MAPI_GAL_ONLY
  
> 仅使用 GAL 执行名称解析。 此标志仅受通讯簿Exchange支持。
    
  > [!NOTE]
  > _ulFlags_ MAPI_GAL_ONLY当前具有的可下载头文件中未定义，在这种情况下，您可以使用以下值将其添加到代码中：>`#define MAPI_GAL_ONLY (0x00000080)`
  
MAPI_MODIFY 
  
> 请求使用读/写权限打开条目。 由于默认情况下使用只读访问权限打开条目，因此客户端不应假定已授予读/写权限，MAPI_MODIFY权限。
    
MAPI_NO_CACHE
  
> 请勿使用脱机通讯簿执行名称解析。 此标志仅受通讯簿Exchange支持。
    
_lpulObjType_
  
> [out]指向打开的条目类型的指针。
    
_lppUnk_
  
> [out]指向已打开条目的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开条目。
    
MAPI_E_NO_ACCESS 
  
> 试图打开用户权限不足的条目。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID 表示_ 的条目不存在。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 无法识别  _lpEntryID 中_ 指定的条目标识符。 如果负责相应条目的通讯簿提供程序未打开，则通常返回此值。 
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **IAddrBook：：OpenEntry** 方法来打开通讯簿条目。 MAPI 根据传入 _lpEntryID_ 参数的条目标识符中包含的 [MAPIUID](mapiuid.md)结构，将呼叫转发到相应的通讯簿提供程序。 除非设置了  _ulFlags_ 参数中的 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，否则通讯簿提供程序会以只读MAPI_BEST_ACCESS打开条目。 但是，这些标志是建议。 如果通讯簿提供程序不允许修改所请求的条目，它将返回MAPI_E_NO_ACCESS。 
  
_lpInterface_ 参数指示应该使用哪个接口来访问打开的条目。 在  _lpInterface 中_ 传递 NULL 表示应该使用该条目类型的标准 MAPI 接口。 由于通讯簿提供程序可能返回的接口与  _lpInterface_ 参数建议的不同，因此呼叫者应检查  _lpulObjType_ 参数中返回的值，以确定返回的 对象类型 是否是预期结果。 如果对象类型类型不是预期类型，则调用方可以将  _lppUnk_ 参数强制转换到更合适的类型。 
  
## <a name="see-also"></a>另请参阅

- [IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

