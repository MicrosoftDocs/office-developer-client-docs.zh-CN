---
title: IMAPISessionOpenMsgStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenMsgStore
api_type:
- COM
ms.assetid: 7f73b5cf-7093-42e9-8acc-63d73df77cf5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19d3df004676a71e2bf6243d9288efd824d99c33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325765"
---
# <a name="imapisessionopenmsgstore"></a>IMAPISession::OpenMsgStore

**适用于**：Outlook 2013 | Outlook 2016 
  
打开邮件存储, 并返回一个[IMsgStore](imsgstoreimapiprop.md)指针以供进一步访问。 
  
```cpp
HRESULT OpenMsgStore(
  ULONG_PTR ulUIParam,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMDB FAR * lppMDB
);
```

## <a name="parameters"></a>参数

_ulUIParam_
  
> 实时公用地址对话框和其他相关显示的父窗口的句柄。
    
_cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
_lpEntryID_
  
> 实时指向要打开的邮件存储区的条目标识符的指针。 _lpEntryID_参数不能为 NULL。 
    
_lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问邮件存储区的接口。 传递 NULL 会导致_lppMDB_参数返回指向邮件存储 (**IMsgStore**) 的标准接口的指针。
    
_ulFlags_
  
> 实时用于控制对象打开方式的标志的位掩码。 可以使用以下标志:
    
  - MAPI_BEST_ACCESS: 请求使用用户允许的最大网络权限和最大客户端应用程序权限打开邮件存储区。 例如, 如果客户端具有读/写权限, 则应使用读/写权限打开邮件存储区;如果客户端具有只读权限, 则应使用只读权限打开邮件存储区。 
      
  - MAPI_DEFERRED_ERRORS: 允许**OpenMsgStore**成功返回, 这可能在邮件存储库完全提供给呼叫客户端之前。 如果邮件存储不可用, 则进行后续的对象调用可能会引发错误。 
      
  - MDB\_NO_DIALOG: 禁止显示登录对话框。 如果设置了此标志, 并且**OpenMsgStore**没有足够的配置信息, 无法在用户帮助下打开邮件存储区, 则将返回 MAPI_E_LOGON_FAILED。 如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码, 或者执行建立与邮件存储的连接所需的其他操作。 
      
  - MDB\_NO_MAIL: 不应使用邮件存储来发送或接收邮件。 设置此标志后, mapi 将不会通知 mapi 后台处理程序正在打开此邮件存储。
      
  - MDB\_ONLINE: 在缓存 Exchange 模式中, 客户端或服务提供程序可以使用 MDB_ONLINE 调用此方法, 以覆盖与本地邮件存储区的连接并在远程服务器上打开存储。 无法同时在缓存模式和非缓存模式下打开同一 MAPI 会话中的 Exchange 存储。 如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。
      
  - MDB_TEMPORARY: 指示 MAPI 邮件存储区不是永久的, 不应将其添加到邮件存储库表中。 此标志用于登录到邮件存储区, 以便可以从 "配置文件" 部分以编程方式检索信息。 
      
  - MDB_WRITE: 请求对邮件存储区的读/写权限。
    
_lppMDB_
  
> 排除指向邮件存储区的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件存储已成功打开。
    
MAPI_E_NO_ACCESS 
  
> 试图访问用户具有的权限不足的邮件存储区。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_指示的邮件存储不存在。 
    
MAPI_E_UNKNOWN_CPID 
  
> 未将服务器配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 未将服务器配置为支持客户端的区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功, 但邮件存储区提供程序有可用的错误信息。 返回此警告时, 应以成功的方式处理该调用。 若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPISession:: OpenMsgStore**方法打开特定的邮件存储区。 
  
## <a name="notes-to-callers"></a>给调用方的说明

邮件存储区的默认权限级别为只读。 如果设置了 MDB_WRITE 标志, 则仍可能无法授予您读/写权限。 MAPI 为邮件存储分配的最终访问级别取决于您的权限级别、邮件存储区本身和邮件存储提供程序。 
  
如果调用**OpenMsgStore**以打开具有只读权限的邮件存储区, 将发生以下情况: 
  
- store 的**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会设置其 store\_MODIFY_OK 和 store\_CREATE_OK bits。 
    
- 通过使用[IMAPISession:: OpenEntry](imapisession-openentry.md)和 MAPI_MODIFY 标志设置来打开邮件存储区中的邮件或文件夹的调用将失败。 
    
- 通过使用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)和 MAPI_MODIFY 标志打开邮件存储的邮件或文件夹的属性之一的调用将失败。 
    
- 对以下任一方法的调用将失败: 
    
  - [IMAPIFolder::CreateMessage](imapifolder-createmessage.md)
    
  - [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
    
  - [IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
    
  - [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md)
    
  - [IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
    
  - [IMAPIProp::SetProps](imapiprop-setprops.md)
    
  - [IMAPIProp::DeleteProps](imapiprop-deleteprops.md)
  
- 如果复制的邮件的目标是只读的, 无论目标是与源邮件存储一样还是另一个只读存储, 则对以下方法的调用将失败。
    
  - [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
  - [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
  - [IMAPIProp::CopyTo](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIStoreFunctions  <br/> |CallOpenMsgStore  <br/> |MFCMAPI 使用**IMAPISession:: OpenMsgStore**方法打开邮件存储区。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
- [IMAPISession::GetLastError](imapisession-getlasterror.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
- [IMAPIProp::OpenProperty](imapiprop-openproperty.md)
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
- [使用宏进行错误处理](using-macros-for-error-handling.md)

