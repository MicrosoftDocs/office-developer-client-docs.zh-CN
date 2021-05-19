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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418020"
---
# <a name="imapisessionopenmsgstore"></a>IMAPISession::OpenMsgStore

**适用于**：Outlook 2013 | Outlook 2016 
  
打开邮件存储并返回 [IMsgStore](imsgstoreimapiprop.md) 指针以进一步访问。 
  
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
  
> [in]常见地址对话框和其他相关显示器的父窗口的句柄。
    
_cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
_lpEntryID_
  
> [in]指向要打开的邮件存储的条目标识符的指针。 _lpEntryID_ 参数不能为 NULL。 
    
_lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问邮件存储的接口的 IID 标识符。 传递 NULL 会导致  _lppMDB_ 参数返回指向 **IMsgStore** (标准接口) 。
    
_ulFlags_
  
> [in]控制对象打开方式的标志的位掩码。 可以使用以下标志：
    
  - MAPI_BEST_ACCESS：请求使用用户允许的最大网络权限和最大客户端应用程序权限打开邮件存储。 例如，如果客户端具有读/写权限，则应该使用读/写权限打开邮件存储;如果客户端具有只读权限，则应该使用只读权限打开邮件存储。 
      
  - MAPI_DEFERRED_ERRORS：允许在邮件存储完全可供调用客户端使用之前，成功返回 **OpenMsgStore。** 如果邮件存储不可用，则进行后续对象调用可能会引发错误。 
      
  - MDB \_ NO_DIALOG：禁止显示登录对话框。 如果设置了此标志，并且 **OpenMsgStore** 的配置信息不足，在没有用户帮助的情况下打开邮件存储，它将返回MAPI_E_LOGON_FAILED。 如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码或执行建立与邮件存储的连接所需的其他操作。 
      
  - MDB NO_MAIL：邮件存储不应 \_ 用于发送或接收邮件。 设置此标志后，MAPI 不会通知 MAPI 后台处理程序此邮件存储正在打开。
      
  - MDB ONLINE：在缓存Exchange模式下，客户端或服务提供商可以使用 MDB_ONLINE 调用此方法以覆盖与本地邮件存储的连接，并打开远程 \_ 服务器上存储。 不能在同一 MAPI 会话中Exchange缓存模式和非缓存模式下同时打开缓存存储。 如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。
      
  - MDB_TEMPORARY：指示 MAPI 邮件存储不是永久性的，不应添加到邮件存储表中。 此标志用于登录到邮件存储，以便可以通过编程方式从配置文件部分检索信息。 
      
  - MDB_WRITE：请求对邮件存储的读/写权限。
    
_lppMDB_
  
> [out]指向消息存储的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开邮件存储。
    
MAPI_E_NO_ACCESS 
  
> 尝试访问用户权限不足的邮件存储。
    
MAPI_E_NOT_FOUND 
  
> _lpEntryID_ 指示的邮件存储不存在。 
    
MAPI_E_UNKNOWN_CPID 
  
> 服务器未配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 服务器未配置为支持客户端区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但邮件存储提供程序提供错误信息。 返回此警告时，应成功处理呼叫。 若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISession：：OpenMsgStore** 方法打开特定邮件存储。 
  
## <a name="notes-to-callers"></a>给调用方的说明

邮件存储的默认权限级别为只读。 如果您设置MDB_WRITE，您仍可能不会被授予读/写权限。 MAPI 分配给邮件存储的最终访问级别取决于您的权限级别、邮件存储本身以及邮件存储提供程序。 
  
如果调用 **OpenMsgStore** 以使用只读权限打开邮件存储，将发生以下情况： 
  
- 存储的 **PR \_** STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会设置其 STORE MODIFY_OK STORE CREATE_OK \_ \_ 位。 
    
- 调用使用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 打开邮件存储的邮件或文件夹之一，MAPI_MODIFY设置失败。 
    
- 调用使用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 和 MAPI_MODIFY 标志打开邮件存储的邮件或文件夹的属性之一将失败。 
    
- 调用以下任一方法将失败： 
    
  - [IMAPIFolder::CreateMessage](imapifolder-createmessage.md)
    
  - [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
    
  - [IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
    
  - [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md)
    
  - [IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
    
  - [IMAPIProp::SetProps](imapiprop-setprops.md)
    
  - [IMAPIProp::DeleteProps](imapiprop-deleteprops.md)
  
- 如果复制的邮件的目标为只读，则对以下方法的调用将失败，无论目标与源邮件存储相同还是另一个只读存储。
    
  - [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
  - [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
  - [IMAPIProp::CopyTo](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIStoreFunctions.cpp  <br/> |CallOpenMsgStore  <br/> |MFCMAPI 使用 **IMAPISession：：OpenMsgStore** 方法打开邮件存储。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
- [IMAPISession::GetLastError](imapisession-getlasterror.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
- [IMAPIProp::OpenProperty](imapiprop-openproperty.md)
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
- [使用宏处理错误](using-macros-for-error-handling.md)

