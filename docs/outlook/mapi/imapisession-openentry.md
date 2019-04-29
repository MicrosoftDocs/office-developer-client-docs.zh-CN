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
ms.openlocfilehash: 10992fdf53c416c473b90b5748b9c5fa4f65cffc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426385"
---
# <a name="imapisessionopenentry"></a>IMAPISession::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开一个对象, 并返回一个接口指针以供其他访问。
  
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
  
> 实时指向要打开的对象的条目标识符的指针。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问打开的对象的接口。 传递 NULL 将返回对象的标准接口。 例如, 如果要打开的对象是一条消息, 则标准接口是[IMessage](imessageimapiprop.md);对于文件夹, 它是[IMAPIFolder](imapifolderimapicontainer.md)。 通讯簿对象的标准接口是[IDistList](idistlistimapicontainer.md)用于邮件用户的通讯组列表和[IMailUser](imailuserimapiprop.md) 。 
    
 _ulFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以使用以下标志:
    
MAPI_BEST_ACCESS 
  
> 使用用户所允许的最大网络权限和最大客户端应用程序访问权限来请求打开对象。 例如, 如果客户端具有读/写权限, 则应以读/写权限打开该对象;如果客户端具有只读权限, 则应以只读权限打开该对象。 
    
MAPI_CACHE_OK
  
> 使用所有方法 (包括脱机通讯簿) 执行名称解析。
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**成功返回, 这可能是在对象完全可用于调用客户端之前。 如果该对象不可用, 则进行后续的对象调用可能会导致错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读权限打开对象, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
MAPI_NO_CACHE
  
> 请勿使用脱机通讯簿执行名称解析。 仅 Exchange 通讯簿提供程序支持此标志。
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目 (即, 它们处于 "已删除邮件" 保留时间阶段)。
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppUnk_
  
> 排除指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对象已成功打开。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读的对象, 或试图访问用户对其权限不足的某个对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_参数中传递的条目标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 在_lpEntryID_参数中传递的条目标识符的格式无法识别。 如果包含该对象的服务提供程序未打开, 则通常会返回此值。 
    
## <a name="remarks"></a>说明

**IMAPISession:: OpenEntry**方法打开一个邮件存储或通讯簿对象, 返回指向可用于访问该对象的接口的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

> [!IMPORTANT]
> 在公用存储 (如文件夹和邮件) 上打开文件夹条目时, 请使用[IMsgStore:: OpenEntry](imsgstore-openentry.md)而不是**IMAPISession:: OpenEntry**。 这样可确保公用文件夹在配置文件中定义了多个 Exchange 帐户时能够正常工作。 
  
仅当您不知道要打开的对象类型时, 才会调用**IMAPISession:: OpenEntry** 。 如果您知道要打开文件夹或邮件, 请调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)。 如果您知道要打开通讯簿容器、邮件用户或通讯组列表, 请调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。 这些更具体的方法比**IMAPISession:: OpenEntry**更快。 
  
MAPI 打开所有具有只读权限的对象, 除非您在_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。 设置其中一个标志并不能保证特定类型的访问权限;授予的权限取决于服务提供商、访问级别和对象。 若要确定打开的对象的访问级别, 请检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
调用**IMAPISession:: OpenEntry**并将_lpEntryID_设置为指向邮件存储项的条目标识符, 与调用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法设置的 MDB_NO_DIALOG 标志相同。 标志设置也是等效的, 但若要请求使用**OpenMsgStore**的读/写权限, 则必须设置 MDB_WRITE 标志而不是 MAPI_MODIFY。 
  
检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是否是您所需的。 如果对象类型不是您所需的类型, 请将指针从_lppUnk_参数转换为适当类型的指针。 例如, 如果您打开一个文件夹, 则会将_lppUnk_转换为 LPMAPIFOLDER 类型的指针。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用**IMAPISession:: OpenEntry**方法打开对象。  <br/> |
   
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

