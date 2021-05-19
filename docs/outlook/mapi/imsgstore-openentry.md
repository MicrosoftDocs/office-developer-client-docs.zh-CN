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
ms.openlocfilehash: 07667558a21a9110d684164d2e6c143d6a519368
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409333"
---
# <a name="imsgstoreopenentry"></a>IMsgStore::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开文件夹或邮件并返回接口指针以进一步访问。 
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数  _。_
    
 _lpEntryID_
  
> [in]指向要打开的对象的条目标识符的指针，或 NULL。 如果  _lpEntryID_ 设置为 **NULL，OpenEntry** 将打开邮件存储的根文件夹。 
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。 传递 NULL 会导致对象的标准接口为 ([IMAPIFolder，](imapifolderimapicontainer.md)对于要返回的邮件，则[) IMessage。](imessageimapiprop.md) 
    
 _ulFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以使用以下标志：
    
MAPI_BEST_ACCESS 
  
> 请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。 如果该对象不可用，则进行后续对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限打开对象，客户端不应在授予读/写权限的假设下工作。 
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppUnk_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象或访问用户权限不足的对象。
    
MAPI_NO_CACHE
  
> 在缓存模式下打开存储区时，客户端或服务提供商可以调用 **IMsgStore：：OpenEntry，** 设置 MAPI_NO_CACHE 标志以打开远程存储上的项目或文件夹。 如果在远程服务器上使用 MDB_ONLINE 标志打开邮件存储，则不需要使用 MAPI_NO_CACHE 标志。
    
## <a name="remarks"></a>备注

**IMsgStore：：OpenEntry** 方法打开文件夹或邮件，并返回一个指向可用于进一步访问的接口的指针。 
  
> [!IMPORTANT]
> 打开公用存储上的文件夹条目（如文件夹和邮件）时，请使用 **IMsgStore：：OpenEntry** 而不是 [IMAPISession：：OpenEntry](imapisession-openentry.md)。 这可确保在配置文件中定义多个Exchange时公用文件夹能够正常运行。 
  
## <a name="notes-to-callers"></a>给调用方的说明

除非您在  _ulFlags_ 参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，否则文件夹和邮件将自动以只读权限打开。 设置其中一个标志并不能保证特定类型的权限;授予的权限取决于邮件存储提供程序、访问级别和对象。 若要确定打开的对象的访问级别，请检索该对象PR_ACCESS_LEVEL ( [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
虽然 **IMsgStore：：OpenEntry** 可用于打开任何文件夹或邮件，但如果可以访问要打开的文件夹或邮件的父文件夹，则使用 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md) 方法通常更快。 
  
检查  _lpulObjType_ 参数中返回的值，以确定返回对象类型的值是否如您预期的那样。 如果对象类型不是预期类型，将指针从  _lppUnk_ 参数强制转换到相应类型的指针。 例如，如果要打开文件夹，将  _lppUnk_ 强制转换到 **类型 LPMAPIFOLDER 的指针**。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用 **IMsgStore：：OpenEntry** 方法打开与条目 ID 关联的对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

