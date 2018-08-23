---
title: IMAPISessionOpenEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenEntry
api_type:
- COM
ms.assetid: a4df4860-cf4f-4e97-97c4-fcd89b7f1f91
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6234fc737857a7e35f562703802f81ff154b3ee6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591012"
---
# <a name="imapisessionopenentry"></a>IMAPISession::OpenEntry

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开一个对象并返回的额外访问的接口指针。
  
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
  
> [in]指向要打开的对象的项标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。 如果传递 NULL 返回对象的标准接口。 例如，如果要在打开的对象是一条消息，标准接口是[IMessage](imessageimapiprop.md);对于文件夹，则[IMAPIFolder](imapifolderimapicontainer.md)。 地址簿对象的标准接口是[IDistList](idistlistimapicontainer.md)通讯组列表和[IMailUser](imailuserimapiprop.md)消息用户。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以使用以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求，通过使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。 例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读权限，则应具有只读权限打开对象。 
    
MAPI_CACHE_OK
  
> 使用所有表示，包括脱机通讯簿执行名称解析。
    
MAPI_CACHE_ONLY
  
> 使用仅脱机通讯簿执行名称解析。 例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。 如果对象不可用，则进行后续对象呼叫会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读权限和客户端应不起作用以为，读/写授予权限。 
    
MAPI_NO_CACHE
  
> 不使用脱机通讯簿执行名称解析。 此标志仅受 Exchange 通讯簿提供程序支持。
    
SHOW_SOFT_DELETES
  
> 显示项目的当前标记为软删除 （即，它们是中已删除的邮件保留时间阶段）。
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppUnk_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 尝试修改只读对象或尝试访问其用户没有足够的权限的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_参数中传递的项标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 无法识别格式_lpEntryID_参数中传递的项标识符。 如果服务提供商的包含对象未打开，则通常会返回此值。 
    
## <a name="remarks"></a>注解

**IMAPISession::OpenEntry**方法打开邮件存储或通讯簿对象，为接口返回指针可用于访问该对象。 
  
## <a name="notes-to-callers"></a>给调用方的说明

> [!IMPORTANT]
> 当打开文件夹释公用的存储，如文件夹和消息，而不是**IMAPISession::OpenEntry**使用[IMsgStore::OpenEntry](imsgstore-openentry.md) 。 这确保公用文件夹正常配置文件中定义了多个 Exchange 帐户。 
  
仅当您不知道哪种类型的对象，您打开时，请调用**IMAPISession::OpenEntry** 。 如果您知道您打开文件夹或一条消息，请调用[IMsgStore::OpenEntry](imsgstore-openentry.md)。 如果您知道您要打开通讯簿容器、 邮件用户或通讯组列表，请调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)。 这些更加具体方法是比**IMAPISession::OpenEntry**速度更快。 
  
MAPI 具有只读权限，除非您将 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志设置_ulFlags_参数中，将打开所有对象。 这些标志之一设置不保证特定类型的访问;授予的权限取决于服务提供程序、 的访问级别，和的对象。 若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
调用**IMAPISession::OpenEntry**和设置_lpEntryID_以指向的消息存储的项标识符调用与 MDB_NO_DIALOG 标志[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法相同设置。 标志设置也是等效的只不过到与**OpenMsgStore**请求读/写权限，则必须设置而不是 MAPI_MODIFY MDB_WRITE 标志。 
  
检查以确定是否返回的对象类型是您的预期_lpulObjType_参数中返回的值。 如果对象类型不是预期的类型，强制转换为适当类型的指针的指针从_lppUnk_参数。 例如，如果您打开一个文件夹，强制转换为的类型 LPMAPIFOLDER 指针_lppUnk_ 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用**IMAPISession::OpenEntry**方法打开一个对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IAddrBook::OpenEntry](iaddrbook-openentry.md)
  
[IDistList : IMAPIContainer](idistlistimapicontainer.md)
  
[IMailUser : IMAPIProp](imailuserimapiprop.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
  
[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)
  
[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

