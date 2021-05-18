---
title: OpenIMsgOnIStg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- OpenIMsgOnIStg
api_type:
- HeaderDef
ms.assetid: a98b0b26-9b19-44ca-9b4e-0ad4d1c54325
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d5ed20e532f0893757cc46d9ea478c7b65acc86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406519"
---
# <a name="openimsgonistg"></a>OpenIMsgOnIStg

**适用于**：Outlook 2013 | Outlook 2016 
  
在邮件会话中使用的现有 OLE **IStorage** 对象的基础上构建一个新的 [IMessage](imessageimapiprop.md)对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE OpenIMsgOnIStg(
  LPMSGSESS lpMsgSess,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  LPMALLOC lpmalloc,
  LPVOID lpMapiSup,
  LPSTORAGE lpStg,
  MSGCALLRELEASE FAR * lpfMsgCallRelease,
  ULONG ulCallerData,
  ULONG ulFlags,
  LPMESSAGE FAR * lppMsg
);
```

## <a name="parameters"></a>参数

_lpMsgSess_
  
> [in]指向将在其中新建 **IMessage**-on- **IStorage** 对象的邮件会话对象的指针。 
    
_lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
_lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。 
    
_lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
_lpMalloc_
  
> [in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。 使用 IStorage 和 **IStream** 等接口时 **，IMessage** 接口需要使用此分配方法。  
    
_lpMapiSup_
  
> [in]指向 MAPI 支持对象的可选指针，服务提供商可以使用该对象调用 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 接口的方法。 
    
_lpStg_
  
> [in， out]指向打开并且具有只读或读/写权限的 OLE **IStorage** 对象的指针。 由于 **IMessage** 不支持仅写访问， **因此 OpenIMsgOnIStg** 不接受在仅写模式下打开的存储对象。 
    
_lpfMsgCallRelease_
  
> [in]基于 [MSGCALLRELEASE](msgcallrelease.md) 原型的回调函数的可选指针，MAPI 在 **IMessage**-on- **IStorage** 对象上一次发布后调用该原型。 
    
_ulCallerData_
  
> [in]MAPI 保存的调用方数据与 **IMessage**-on- **IStorage** 对象一起，并传递到基于 **MSGCALLRELEASE** 的回调函数。 该数据提供有关要释放的 **IMessage** 对象以及生成该对象顶部的 **IStorage** 对象的上下文。 
    
_ulFlags_
  
> [in]用于控制当客户端应用程序或服务提供商调用 **IMessage：：SaveChanges** 方法时是否调用 OLE **IStorage：：Commit** 方法的标志的位掩码。 可以设置以下标志： 
    
IMSG_NO_ISTG_COMMIT 
  
> 当客户端或提供程序调用 [SaveChanges](imapiprop-savechanges.md)时，不会调用 OLE 方法 **IStorage：：Commit。** 
    
MAPI_UNICODE
  
> 允许创建 Unicode .msg 文件。 生成的 [IMessage](imessageimapiprop.md) 文件在其 [STORE_UNICODE_OK中显示](pidtagstoresupportmask-canonical-property.md) PR_STORE_SUPPORT_MASK并支持 Unicode 属性。 
    
  > [!NOTE]
  > 仅在 MAPI_UNICODE 2003 或更高版本上的此函数Outlook该标记。 
  
_lppMsg_
  
> [out]指向打开的 **IMessage** 对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

只能在属性对象（即实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口的对象）上访问属性属性。 若要使 MAPI 属性在 OLE 结构化存储对象上可用 **，OpenIMsgOnIStg** 在 OLE **IStorage** 对象顶部构建 [IMessage ： IMAPIProp](imessageimapiprop.md)对象。 可以使用 [SetAttribIMsgOnIStg](setattribimsgonistg.md) 设置或更改此类对象的属性属性，然后使用 [GetAttribIMsgOnIStg 进行检索](getattribimsgonistg.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用 **OpenIMsgOnIStg** 之前，应该使用 [OpenIMsgSession](openimsgsession.md)打开邮件会话。 提供有效的  _lpMsgSess_ 参数确保新邮件是在邮件会话中创建的，因此在会话关闭时该邮件将关闭。 如果  _lpMsgSess_ 为 NULL，则独立于任何邮件会话创建邮件。 如果创建邮件的客户端应用程序或服务提供商未释放邮件及其所有附件和打开的表，则内存会泄露，并可能导致应用程序终止。 
  
MAPI 使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和处理，尤其是当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，分配供客户端应用程序使用的内存。  当使用有效的 _lpMapiSup_ 参数调用 **OpenIMsgOnIStg** 函数时 _，lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指针是可选的。  
  
因为它处理的是基础 OLE 对象，所以 MAPI 还需要使用 OLE 内存分配。 有关 OLE 结构化存储对象和 OLE 内存分配的信息，请参阅 _《OLE 程序员参考》。_ 
  
如果  _为 lpMapiSup_ 提供了有效值， **则 IMessage** 支持 MAPI_DIALOG 和 ATTACH_DIALOG 标志，方法是调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法为 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMessage：:D eleteAttach](imessage-deleteattach.md) 方法提供进度用户界面。 此外 [，IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法尝试通过调用 [IMAPISupport：：OpenAddressBook](imapisupport-openaddressbook.md) 方法并调用生成的通讯簿对象，将短期条目标识符转换为长期条目标识符。 如果为  _lpMapiSup_ 传递 NULL， **则 IMessage** 将忽略 MAPI_DIALOG 和 ATTACH_DIALOG 并存储短期条目标识符而不进行转换。 
  
_lpStg_ 参数指向的 **IStorage** 对象必须在 STGM_READ 或 STGM_READWRITE 模式下打开。 如果使用STGM_READWRITE模式，则还必须STGM_TRANSACTED模式。 
  
_lpfMsgCallRelease_ 参数指向的回调函数是可选的;如果提供，则它应基于 [MSGCALLRELEASE](msgcallrelease.md)函数原型。 **当最后一次调用 IMessage** -on- IStorage 对象的引用计数设置为零时 **，IMessage** 接口将 **调用** 它。  回调函数通常用于释放基础 **IStorage** 接口。 **执行回调后，IMessage** 不会尝试访问 _lpStg_ 参数指向的 **IStorage** 对象。 
  
某些客户端或提供程序可能会向 **IStorage** 对象写入超出 **IMessage** 本身在调用 [SaveChanges](imapiprop-savechanges.md) 方法时写入的数据。 客户端或提供程序可以使用 IMSG_NO_ISTG_COMMIT 标志来阻止 **IMessage** 在处理 **SaveChanges** 调用时调用 OLE **IStorage：：Commit** 方法;在这种情况下，客户端或提供程序必须在写入其他数据时自行提交 **IStorage** 对象。 为帮助实现此目的 **，IMessage** 实现保证在 **IStorage** 对象（以字符串"__"开头，即用两个下划线字符）创建的所有子存储命名。 客户端或提供程序可以通过将子存储名称排除在此命名空间外来避免名称冲突。 
  
MAPI 不定义对邮件的子对象（如附件、流或嵌入邮件）执行多个打开操作的行为。 MAPI 当前允许再次打开已打开的子对象，但 MAPI 通过增加现有打开对象的引用计数，并返回到调用 [IMessage：：OpenAttach](imessage-openattach.md) 或 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法的客户端或提供程序来执行打开操作。 这意味着，针对子对象上的第一个打开操作请求的访问是提供给所有后续打开操作的访问，而不考虑这些操作请求的访问。 
  
将邮件放入附件的正确过程是调用接口标识符为 IID_IMessage 的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法。 **OpenProperty** 当前还支持创建直接在 OLE **IStorage** 接口上可用的邮件附件，IID_IStorage标识符。 **支持 IStorage** 访问，以允许一种简便Microsoft Word将文档放入附件，而无需将其转换为 OLE **IStream** 接口或从该接口转换。 但是，如果将 **IStorage** 指针传递给附件数据的 **OpenIMsgOnIStg，** 然后对象按错误的顺序释放，则 **IMessage** 的行为可能无法预测。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |LoadMSGToMessage  <br/> |MFCMAPI 使用 **OpenIMsgOnIStg** 方法在 上打开 IMessage 接口。MSG 文件，以便使用 MAPI 处理该文件。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

