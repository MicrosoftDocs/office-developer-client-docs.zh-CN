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
description: 上次修改时间： 2013 年 2 月 1 日
ms.openlocfilehash: fa279962043f6f7cb7a134b624000c9c7e65369f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19775263"
---
# <a name="iaddrbookopenentry"></a>IAddrBook::OpenEntry

**适用于**： Outlook 
  
打开的通讯簿条目，并返回可用于访问该条目的接口的指针。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
_lpEntryID_
  
> [in]一个指向代表打开的通讯簿条目的项标识符。
    
_lpInterface_
  
> [in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。 如果传递 NULL 返回对象的标准接口。 对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。 对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。 
    
_ulFlags_
  
> [in]位掩码的标志，控制如何打开该条目。 可以设置以下标志。
    
MAPI_BEST_ACCESS 
  
> 与最大允许网络和客户端权限打开的条目的请求。 例如，如果客户端具有读/写权限，通讯簿提供程序应尝试打开具有读/写权限条目。 客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性授予的访问级别。
    
MAPI_CACHE_ONLY
  
> 打开的通讯簿条目，并访问仅从缓存。 例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_DEFERRED_ERRORS 
  
> 允许的调用成功，可能之前该条目是完全打开且可用，这意味着更高版本调用条目可能会返回错误。
    
MAPI_GAL_ONLY
  
> 使用仅 GAL 执行名称解析。 此标志仅受 Exchange 通讯簿提供程序支持。
    
  > [!NOTE]
  > _UlFlags_ MAPI_GAL_ONLY 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define MAPI_GAL_ONLY (0x00000080)`
  
MAPI_MODIFY 
  
> 请求项打开的读/写权限。 因为条目具有只读访问权限打开默认情况下，客户端不应假定无论是否设置 MAPI_MODIFY 授予了读/写权限。
    
MAPI_NO_CACHE
  
> 不使用脱机通讯簿执行名称解析。 此标志仅受 Exchange 通讯簿提供程序支持。
    
_lpulObjType_
  
> [输出]一个指向打开条目的类型。
    
_lppUnk_
  
> [输出]指向于打开项的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开该条目。
    
MAPI_E_NO_ACCESS 
  
> 尝试打开其用户没有足够的权限条目。
    
MAPI_E_NOT_FOUND 
  
> 由_lpEntryID_项不存在。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 无法识别_lpEntryID_中指定的项标识符。 如果负责的相应条目的地址簿提供程序未打开，则通常会返回此值。 
    
## <a name="remarks"></a>注解

客户端和服务提供商调用**IAddrBook::OpenEntry**方法打开的通讯簿条目。 MAPI 转发到适当的地址簿提供程序，基于[MAPIUID](mapiuid.md)结构包含传递_lpEntryID_参数中的项标识符的调用。 通讯簿提供程序将打开以只读方式条目，除非设置了_ulFlags_参数中的 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 但是，这些标志为建议。 如果通讯簿提供程序不允许请求的项的修改，则将返回 MAPI_E_NO_ACCESS。 
  
_LpInterface_参数指示应使用哪个接口访问打开的条目。 在_lpInterface_传递 NULL 指示应使用标准的 MAPI 接口，该类型的项。 因为通讯簿提供程序可能返回不同的接口，建议_lpInterface_参数比，呼叫者应检查以确定是否返回的对象类型是在_lpulObjType_参数中返回的值预期的。 如果对象类型不是预期的类型，调用方可以强制转换更适合的类型_lppUnk_参数。 
  
## <a name="see-also"></a>另请参阅

- [IAddrBook: IMAPIProp](iaddrbookimapiprop.md)

