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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309693"
---
# <a name="imsgstoreopenentry"></a>IMsgStore::OpenEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开一个文件夹或邮件, 并返回一个接口指针以供进一步访问。 
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数 _。_
    
 _lpEntryID_
  
> 实时指向要打开的对象的条目标识符的指针, 或 NULL。 如果将_lpEntryID_设置为 NULL, **OpenEntry**将打开邮件存储区的根文件夹。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问打开的对象的接口。 在对象的标准接口 ([IMAPIFolder](imapifolderimapicontainer.md)文件夹和[IMessage](imessageimapiprop.md)中的邮件) 中传递 NULL 结果。 
    
 _ulFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以使用以下标志:
    
MAPI_BEST_ACCESS 
  
> 使用用户所允许的最大网络权限和最大客户端应用程序访问权限来请求打开对象。 例如, 如果客户端具有读/写权限, 则应使用读/写权限打开该对象;如果客户端具有只读权限, 则应使用只读权限打开该对象。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenEntry**成功返回, 这可能是在对象完全可用于调用客户端之前。 如果该对象不可用, 则进行后续的对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读权限打开对象, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppUnk_
  
> 排除指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象或访问用户拥有的对象权限不足的对象。
    
MAPI_NO_CACHE
  
> 在缓存模式下打开存储时, 客户端或服务提供程序可以调用**IMsgStore:: OpenEntry**, 将 MAPI_NO_CACHE 标志设置为打开远程存储上的项目或文件夹。 如果使用远程服务器上的 MDB_ONLINE 标志打开邮件存储区, 则无需使用 MAPI_NO_CACHE 标志。
    
## <a name="remarks"></a>注解

**IMsgStore:: OpenEntry**方法打开一个文件夹或邮件, 并返回指向可用于进一步访问的接口的指针。 
  
> [!IMPORTANT]
> 在公用存储 (如文件夹和邮件) 上打开文件夹条目时, 请使用**IMsgStore:: OpenEntry**而不是[IMAPISession:: OpenEntry](imapisession-openentry.md)。 这样可确保公用文件夹在配置文件中定义了多个 Exchange 帐户时能够正常工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

除非您在_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志, 否则会自动以只读权限打开文件夹和邮件。 设置其中一个标志并不能保证特定类型的权限;您授予的权限取决于邮件存储提供程序、您的访问级别和对象。 若要确定打开的对象的访问级别, 请检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。
  
虽然**IMsgStore:: OpenEntry**可用于打开任何文件夹或邮件, 但如果您有权访问要打开的文件夹或邮件的父文件夹, 则使用[IMAPIContainer:: OpenEntry](imapicontainer-openentry.md)方法通常会更快。 
  
检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是否符合您的预期。 如果对象类型不是预期类型, 则将指针从_lppUnk_参数转换为适当类型的指针。 例如, 如果您打开一个文件夹, 则会将_lppUnk_转换为**LPMAPIFOLDER**类型的指针。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |CallOpenEntry  <br/> |MFCMAPI 使用**IMsgStore:: OpenEntry**方法打开与条目 ID 关联的对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

