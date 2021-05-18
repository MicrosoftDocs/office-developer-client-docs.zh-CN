---
title: IABLogonOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenEntry
api_type:
- COM
ms.assetid: 1cfb82f7-5215-4faa-af25-5b1da7e31209
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 70f61ef553350f08eed96c1ee4e9ab790359d1fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409228"
---
# <a name="iablogonopenentry"></a>IABLogon::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开容器、消息传送用户或通讯组列表，并返回指向接口实现以进一步访问的指针。
  
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
  
> [in]指向要打开的容器、消息传送用户或通讯组列表的条目标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。 传递 NULL 将返回对象的标准接口的标识符。 对于容器，标准接口是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。 通讯簿对象的标准接口是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 表示通讯组列表和 [IMailUser ： IMAPIProp](imailuserimapiprop.md) 消息用户。 
    
 _ulFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenEntry** 方法成功返回，可能在调用客户端完全访问对象之前。 如果未访问该对象，则进行后续对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读访问权限打开对象，客户端不应假定已授予读/写权限。
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="remarks"></a>备注

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户没有足够的权限打开对象，或者试图打开具有读/写权限的只读对象。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_ 指定的条目标识符不表示对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_ 参数中的条目标识符不是通讯簿提供程序识别的格式。 
    
## <a name="remarks"></a>备注

MAPI 调用 **OpenEntry** 方法打开容器、邮件传递用户或通讯组列表。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 MAPI 调用 **OpenEntry** 方法之前，它确定  _lpEntryID_ 参数中的条目标识符属于您而不是其他提供程序。 MAPI 通过以下方法实现此操作：将条目标识符中的 [MAPIUID](mapiuid.md)结构与在启动时通过调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)方法注册的 **MAPIUID** 相匹配。 
  
除非在  _ulFlags_ 参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，否则以只读状态打开该对象。 如果您不允许对请求的对象进行修改，则完全不要打开该对象并返回MAPI_E_NO_ACCESS。 
  
如果 MAPI 为  _lpEntryID_ 传递 NULL，请打开容器层次结构中的根容器。
  
要求您打开的对象可能是从另一个提供程序复制的对象。 在这种情况下，它将支持[PidTagTemplateid PR_TEMPLATEID (PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。  如果对象支持此属性，请调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)方法以绑定到在外提供程序中为此条目的代码，在 _lpTemplateID_ 参数中传递 **PR_TEMPLATEID，** 在 _ulTemplateFlags_ 参数中传递 0。 **IMAPISupport：：OpenTemplateID** 在调用外提供程序 [的 IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法时将此信息传递给该外提供程序。 如果 **IMAPISupport：：OpenTemplateID** 引发错误（通常是由于配置文件中的外提供程序不可用或未包含在配置文件中）尝试继续，将未绑定条目视为只读。 有关打开外通讯簿条目的信息，请参阅代理 [主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

