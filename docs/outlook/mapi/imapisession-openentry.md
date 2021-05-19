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
  
打开对象并返回接口指针以用于其他访问。
  
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
  
> [in]指向要打开的对象的条目标识符的指针。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。 传递 NULL 将返回对象的标准接口。 例如，如果要打开的对象是一条消息，则标准接口为 [IMessage](imessageimapiprop.md);对于文件夹，它是 [IMAPIFolder](imapifolderimapicontainer.md)。 通讯簿对象的标准接口是通讯组列表的[IDistList](idistlistimapicontainer.md)和邮件用户的[IMailUser。](imailuserimapiprop.md) 
    
 _ulFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以使用以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。 
    
MAPI_CACHE_OK
  
> 使用所有方法（包括脱机通讯簿）执行名称解析。
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。 如果该对象不可用，则进行后续的对象调用可能会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限打开对象，客户端不应在授予读/写权限的假设下工作。 
    
MAPI_NO_CACHE
  
> 请勿使用脱机通讯簿执行名称解析。 此标志仅受通讯簿Exchange支持。
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目 (即它们处于已删除项目保留时间阶段) 。
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开对象。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象，或试图访问用户权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与在  _lpEntryID_ 参数中传递的条目标识符关联的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 在  _lpEntryID_ 参数中传递的条目标识符采用不可识别的格式。 如果包含该对象的服务提供商未打开，则通常返回此值。 
    
## <a name="remarks"></a>备注

**IMAPISession：：OpenEntry** 方法打开消息存储或通讯簿对象，返回一个指向可用于访问该对象的接口的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

> [!IMPORTANT]
> 打开公用存储上的文件夹条目（如文件夹和邮件）时，请使用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 而不是 **IMAPISession：：OpenEntry**。 这可确保在配置文件中定义多个Exchange时公用文件夹能够正常运行。 
  
仅在不知道要打开哪种类型的对象时调用 **IMAPISession：：OpenEntry。** 如果您知道要打开文件夹或邮件，请调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md)。 如果您知道要打开通讯簿容器、邮件传递用户或通讯组列表，请调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)。 这些更具体的方法比 **IMAPISession：：OpenEntry 快**。 
  
MAPI 以只读权限打开所有对象，除非您在  _ulFlags_ 参数中MAPI_MODIFY或 MAPI_BEST_ACCESS 标记。 设置其中一个标志并不能保证特殊类型的访问;授予的权限取决于服务提供商、访问级别和对象。 若要确定打开的对象的访问级别，请检索该对象PR_ACCESS_LEVEL ( [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
调用 **IMAPISession：：OpenEntry** 并设置  _lpEntryID_ 以指向邮件存储的条目标识符与调用设置了 MDB_NO_DIALOG 标志的 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 方法相同。 标志设置也是等效的，除了使用 **OpenMsgStore** 请求读/写权限外，必须设置 MDB_WRITE 标志，而不是MAPI_MODIFY。 
  
检查  _lpulObjType_ 参数中返回的值，以确定对象类型返回的值是否如您预期的那样。 如果对象类型不是您预期的类型，请从  _lppUnk_ 参数将指针强制转换到相应类型的指针。 例如，如果要打开文件夹，将  _lppUnk_ 强制转换到类型 LPMAPIFOLDER 的指针。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用 **IMAPISession：：OpenEntry** 方法打开对象。  <br/> |
   
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

