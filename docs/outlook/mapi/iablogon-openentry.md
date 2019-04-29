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
  
打开容器、邮件用户或通讯组列表, 并返回指向接口实现的指针, 以提供进一步的访问权限。
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要打开的容器、邮件用户或通讯组列表的条目标识符的指针。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问打开的对象的接口。 传递 NULL 将返回对象的标准接口的标识符。 对于容器, 标准接口为[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。 通讯簿对象的标准接口为[IDistList: IMAPIContainer](idistlistimapicontainer.md)对于邮件用户的通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md) 。 
    
 _ulFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_BEST_ACCESS 
  
> 请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如, 如果客户端具有读/写权限, 则应以读/写权限打开该对象;如果客户端具有只读权限, 则应以只读权限打开该对象。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**方法成功返回, 这可能是在调用客户端完全访问了该对象之前。 如果不访问该对象, 进行后续的对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读访问权限打开对象, 并且客户端不应假定已授予读/写权限。
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppUnk_
  
> 排除指向打开的对象的指针的指针。
    
## <a name="remarks"></a>说明

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 用户的权限不足, 无法打开该对象, 或试图打开具有读/写权限的只读对象。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_指定的条目标识符不代表对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_参数中的条目标识符不是通讯簿提供程序可识别的格式。 
    
## <a name="remarks"></a>说明

MAPI 调用**OpenEntry**方法来打开容器、邮件用户或通讯组列表。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 MAPI 调用您的**OpenEntry**方法之前, 它确定_lpEntryID_参数中的条目标识符属于您而不是另一个提供程序。 MAPI 通过将条目标识符中的[MAPIUID](mapiuid.md)结构与您在启动时调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法注册的**MAPIUID**相匹配的条目标识符来实现此操作。 
  
将对象以只读方式打开, 除非在_ulFlags_参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 如果不允许对所请求的对象进行修改, 请不要打开所有对象, 并返回 MAPI_E_NO_ACCESS。 
  
如果 MAPI 为_lpEntryID_传递了 NULL, 请打开容器层次结构中的根容器。
  
要求您打开的对象可能是从另一个提供程序复制的对象。 在这种情况下, 它将支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 如果该对象不支持此属性, 请调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法, 以在外部提供程序中绑定到此条目的代码, 在_lpTemplateID_参数中传递**PR_TEMPLATEID** , 在 ulTemplateFlags 中传递 0 __ 参数。 **IMAPISupport:: OpenTemplateID**在对外部提供程序的[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法的调用中将此信息传递给外部提供程序。 如果**IMAPISupport:: OpenTemplateID**引发错误, 通常是因为外部提供程序不可用或不包含在配置文件中, 请尝试通过将未绑定项视为只读来继续操作。 有关打开外部通讯簿条目的详细信息, 请参阅[作为主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon : IUnknown](iablogoniunknown.md)

