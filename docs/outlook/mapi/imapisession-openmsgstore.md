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
ms.openlocfilehash: 983c22772acfea7837e85d409b7928a35aed91ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775568"
---
# <a name="imapisessionopenmsgstore"></a>IMAPISession::OpenMsgStore

**适用于**： Outlook 
  
打开的消息存储并返回进一步访问[IMsgStore](imsgstoreimapiprop.md)指针。 
  
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
  
> [in]通用的地址对话框和其他的父窗口的句柄相关显示。
    
_cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
_lpEntryID_
  
> [in]指向要打开的消息存储的项标识符的指针。 _LpEntryID_参数不能为 NULL。 
    
_lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问邮件存储区的接口的指针。 传递 NULL 会导致_lppMDB_参数来返回指向的消息存储 (**IMsgStore**) 的标准接口的指针。
    
_ulFlags_
  
> [in]位掩码的标志，控制如何打开对象。 可以使用以下标志：
    
  - MAPI_BEST_ACCESS： 请求的最大网络权限打开的消息存储和允许的用户的最大客户端应用程序权限。 例如，如果客户端具有读/写权限，消息存储应打开具有读/写权限;如果客户端具有只读权限，应具有只读权限打开的消息存储。 
      
  - MAPI_DEFERRED_ERRORS： 允许**OpenMsgStore**成功返回可能的消息之前存储是完全可调用客户端。 如果消息存储不可用，则进行后续对象呼叫会引发错误。 
      
  - MDB\_NO_DIALOG： 阻止的登录对话框显示。 如果设置此标志，并且**OpenMsgStore**有不足，无法配置的信息来打开消息存储，无需用户的帮助，则将返回 MAPI_E_LOGON_FAILED。 如果未设置此标志，消息存储提供程序可以提示用户更正名或密码或执行其他操作所需的消息存储与建立连接。 
      
  - MDB\_NO_MAIL： 消息存储不应发送或接收邮件。 当设置此标志时，MAPI 不通知 MAPI 后台处理程序打开的时此消息存储。
      
  - MDB\_ONLINE： 在缓存 Exchange 模式，客户端或服务提供程序可以调用此方法与 MDB_ONLINE 覆盖本地消息存储库的连接并打开远程服务器上的存储。 在缓存模式和非缓存模式下在同一 MAPI 会话中的同一时间，您无法打开 Exchange 存储。 如果您已经打开的缓存的消息存储之前，必须也关闭存储打开与此标志，或打开新其中可以使用此标志打开 Exchange 存储的远程服务器上的 MAPI 会话。
      
  - MDB_TEMPORARY： 指示 MAPI 消息存储不是永久性操作和不应添加到消息存储表。 此标志用于登录到的消息存储，因此可以从配置文件部分以编程方式检索信息。 
      
  - MDB_WRITE： 请求读/写权限的邮件存储区。
    
_lppMDB_
  
> [输出]为邮件存储的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 消息存储已成功打开。
    
MAPI_E_NO_ACCESS 
  
> 尝试访问其用户没有足够的权限的消息存储。
    
MAPI_E_NOT_FOUND 
  
> 由_lpEntryID_的消息存储不存在。 
    
MAPI_E_UNKNOWN_CPID 
  
> 将服务器不配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 将服务器不配置为支持客户端的区域设置信息。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功，但消息存储提供程序已经可用的错误信息。 返回此警告时，应处理呼叫为成功。 要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPISession::OpenMsgStore**方法打开特定邮件存储区。 
  
## <a name="notes-to-callers"></a>给调用方的说明

消息存储库的默认权限级别是只读的。 如果设置 MDB_WRITE 标志，您仍可能不被授予读/写权限。 最终的 MAPI 分配到的消息存储取决于您的权限级别的访问级别，邮件存储本身，和消息存储提供程序。 
  
如果调用**OpenMsgStore**具有只读权限打开邮件存储区时，将执行以下操作： 
  
- 存储的**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会其存储\_MODIFY_OK 和存储\_CREATE_OK 位设置。 
    
- 设置了 MAPI_MODIFY 标志使用[IMAPISession::OpenEntry](imapisession-openentry.md)打开之一的消息存储的邮件或文件夹的调用将失败。 
    
- 若要打开的消息存储库的邮件或文件夹的属性之一的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)使用 MAPI_MODIFY 标志的调用将失败。 
    
- 对任何以下方法的调用将失败： 
    
  - [IMAPIFolder::CreateMessage](imapifolder-createmessage.md)
    
  - [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)
    
  - [IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
    
  - [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md)
    
  - [IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)
    
  - [IMAPIProp::SetProps](imapiprop-setprops.md)
    
  - [IMAPIProp::DeleteProps](imapiprop-deleteprops.md)
  
- 如果复制邮件的目标是只读的目标是源消息存储相同还是是另一个只读的存储，对下列方法的调用将失败。
    
  - [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
  - [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
  - [IMAPIProp::CopyTo](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIStoreFunctions.cpp  <br/> |CallOpenMsgStore  <br/> |MFCMAPI 使用**IMAPISession::OpenMsgStore**方法打开的消息存储。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMsgStore : IMAPIProp](imsgstoreimapiprop.md)
- [IMAPISession::GetLastError](imapisession-getlasterror.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
- [IMAPIProp::OpenProperty](imapiprop-openproperty.md)
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
- [使用宏进行错误处理](using-macros-for-error-handling.md)

