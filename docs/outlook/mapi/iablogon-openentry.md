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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 53dfb62bb33a4941e2b5627e729763101e24319d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775211"
---
# <a name="iablogonopenentry"></a>IABLogon::OpenEntry

  
  
**适用于**： Outlook 
  
打开的容器，消息用户或通讯组列表，并返回指向接口实现，以提供更多访问的指针。
  
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
  
> [in]指向该容器，消息用户或通讯组列表，以打开的项标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。 如果传递 NULL 返回对象的标准接口的标识符。 对于容器，标准接口是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 标准接口的地址簿对象是[IDistList: IMAPIContainer](idistlistimapicontainer.md)通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md)消息用户。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以设置以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求的用户和最大客户端应用程序访问允许的最大网络权限打开对象。 例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读权限，则应具有只读权限打开对象。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**方法可返回成功，可能之前调用客户端具有完全访问对象。 如果对象不能访问，则进行后续对象呼叫会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读访问权限和客户端不应假定已被授予读/写权限。
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="remarks"></a>说明

S_OK 
  
> 成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户具有权限不足，无法打开对象，或尝试打开只读对象具有读/写权限。
    
MAPI_E_NOT_FOUND 
  
> 指定_lpEntryID_的项标识符不代表一个对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _LpEntryID_参数中的项标识符不是格式的识别通讯簿提供程序。 
    
## <a name="remarks"></a>说明

MAPI 调用**OpenEntry**方法打开容器中，消息用户或通讯组列表。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

MAPI 调用**OpenEntry**方法之前，它确定_lpEntryID_参数中的项标识符所属给您，而不适用于其他提供程序。 MAPI 匹配具有在启动时调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法来注册**MAPIUID**的项标识符的[MAPIUID](mapiuid.md)结构来达到此目的。 
  
除非 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志设置_ulFlags_参数中打开以只读方式，该对象。 如果不允许请求的对象的修改，不要在所有打开的对象并返回 MAPI_E_NO_ACCESS。 
  
MAPI 的_lpEntryID_传递 NULL，如果您容器层次结构中打开根容器。
  
您需要打开的对象可能是其他提供程序从复制的对象。 在这种情况下，它将支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 如果对象不支持此属性，调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法以绑定到此项在外的提供程序，传递**PR_TEMPLATEID** _lpTemplateID_参数和_ulTemplateFlags 0 中的代码_参数。 **IMAPISupport::OpenTemplateID**将此信息传递给外提供程序的[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法调用中的外提供程序。 如果**IMAPISupport::OpenTemplateID**将引发错误，通常外的提供程序是不可用或不包含在该配置文件，因为尝试继续通过将视为只读的绑定的条目。 打开外的通讯簿条目的详细信息，请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

