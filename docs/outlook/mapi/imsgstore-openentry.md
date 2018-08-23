---
title: IMsgStoreOpenEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.OpenEntry
api_type:
- COM
ms.assetid: a63c42cf-36af-466b-b41e-d6b53ce1c9fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 611680db87c02b9370d6c1b3ac7a8d68b47f3050
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574025"
---
# <a name="imsgstoreopenentry"></a>IMsgStore::OpenEntry

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开文件夹或消息并返回进一步访问的接口指针。 
  
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
  
> [in]_LpEntryID_参数 _。_ 指向该条目标识符中字节数
    
 _lpEntryID_
  
> [in]指向打开，则为 NULL 对象的项标识符的指针。 如果_lpEntryID_设置为 NULL， **OpenEntry**将打开的邮件存储区的根文件夹。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。 传递空结果对象中的返回标准接口 ([IMAPIFolder](imapifolderimapicontainer.md)文件夹) 和[IMessage](imessageimapiprop.md)的邮件。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以使用以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求，通过使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。 例如，如果客户端具有读/写权限，该对象应打开使用读/写权限;如果客户端具有只读权限，则应使用只读权限打开对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。 如果对象不可用，则进行后续对象呼叫会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读权限和客户端应不起作用以为，读/写授予权限。 
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_ACCESS 
  
> 尝试修改只读对象或访问其用户没有足够的权限的对象。
    
MAPI_NO_CACHE
  
> 当在缓存模式下打开存储区时，客户端或服务提供程序可以调用**IMsgStore::OpenEntry**，设置要打开的项目或远程存储上的文件夹的 MAPI_NO_CACHE 标志。 如果您使用 MDB_ONLINE 标志远程服务器上打开的消息存储，您不必使用 MAPI_NO_CACHE 标志。
    
## <a name="remarks"></a>注解

**IMsgStore::OpenEntry**方法打开文件夹或消息，并返回可用于进一步访问的接口的指针。 
  
> [!IMPORTANT]
> 当打开文件夹释公用的存储，如文件夹和消息，而不是[IMAPISession::OpenEntry](imapisession-openentry.md)使用**IMsgStore::OpenEntry** 。 这确保公用文件夹正常配置文件中定义了多个 Exchange 帐户。 
  
## <a name="notes-to-callers"></a>给调用方的说明

文件夹和邮件会自动打开具有只读权限，除非_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 这些标志之一设置不保证特定类型的权限;您已被授予的权限取决于消息存储提供程序、 您的访问级别和的对象。 若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
尽管**IMsgStore::OpenEntry**可用于打开任何文件夹或消息，但它通常是更快地使用[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)方法，如果您具有对打开的邮件的文件夹的父文件夹的访问。 
  
检查以确定是否返回的对象类型是您的预期_lpulObjType_参数中返回的值。 如果对象类型不是预期的类型，强制转换为适当类型的指针的指针从_lppUnk_参数。 例如，如果您打开一个文件夹，强制转换为的类型**LPMAPIFOLDER**指针_lppUnk_ 。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用**IMsgStore::OpenEntry**方法打开与条目 ID 关联的对象  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

