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
  
在现有 OLE **IStorage**对象的顶部生成一个新的[IMessage](imessageimapiprop.md)对象, 以在邮件会话中使用。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时指向要在其中创建新的**IMessage** **IStorage**对象的邮件会话对象的指针。 
    
_lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
_lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。 
    
_lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
_lpMalloc_
  
> 实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。 在使用**IStorage**和**IStream**等接口时, **IMessage**接口需要使用此分配方法。 
    
_lpMapiSup_
  
> 实时指向 MAPI 支持对象的可选指针, 服务提供程序可以使用该指针调用[IMAPISupport: IUnknown](imapisupportiunknown.md)接口的方法。 
    
_lpStg_
  
> [in, out]指向打开且具有只读或读/写权限的 OLE **IStorage**对象的指针。 由于**IMessage**不支持只写访问, 因此**OpenIMsgOnIStg**不接受以只写模式打开的存储对象。 
    
_lpfMsgCallRelease_
  
> 实时指向基于[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数的可选指针, 该函数是 MAPI 在**IMessage**对象上的最后一个版本之后调用的**** 。 
    
_ulCallerData_
  
> 实时MAPI 使用**IMessage**- **IStorage**对象保存的调用方数据, 并传递给基于**MSGCALLRELEASE**的回调函数。 数据提供有关要释放的**IMessage**对象的上下文以及在其上生成该对象的**IStorage**对象。 
    
_ulFlags_
  
> 实时用于控制是否在客户端应用程序或服务提供程序调用**IMessage:: SaveChanges**方法时调用 OLE **IStorage:: Commit**方法的标志的位掩码。 可以设置以下标志: 
    
IMSG_NO_ISTG_COMMIT 
  
> 在客户端或提供程序调用[SaveChanges](imapiprop-savechanges.md)时, 不会调用 OLE 方法**IStorage:: Commit** 。 
    
MAPI_UNICODE
  
> 允许创建 Unicode .msg 文件。 生成的[IMessage](imessageimapiprop.md)文件在其[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)中显示 STORE_UNICODE_OK, 并支持 UNICODE 属性。 
    
  > [!NOTE]
  > 仅在 Outlook 2003 或更高版本的此函数中支持 MAPI_UNICODE 标志。 
  
_lppMsg_
  
> 排除指向打开的**IMessage**对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

只能在属性对象 (即实现[IMAPIProp: IUnknown](imapipropiunknown.md)接口的对象) 上访问属性属性。 若要使 MAPI 属性在 ole 结构化存储对象上可用, **OpenIMsgOnIStg**在 ole **IStorage**对象的顶部生成[IMessage: IMAPIProp](imessageimapiprop.md)对象。 此类对象上的属性属性可以使用[SetAttribIMsgOnIStg](setattribimsgonistg.md)进行设置或更改, 并可使用[GetAttribIMsgOnIStg](getattribimsgonistg.md)进行检索。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用**OpenIMsgOnIStg**之前, 应使用[OpenIMsgSession](openimsgsession.md)打开一个邮件会话。 提供有效的_lpMsgSess_参数使 sures 能够在邮件会话中创建新邮件, 以便在会话关闭时将其关闭。 如果_lpMsgSess_为 NULL, 则不会独立于任何邮件会话创建邮件。 如果创建该邮件的客户端应用程序或服务提供程序不释放它以及它的所有附件和打开的表, 则内存泄漏, 并可能导致应用程序终止。 
  
MAPI 将_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数用于大多数内存分配和释放, 尤其是在调用对象接口时分配内存供客户端应用程序使用。例如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。 使用有效的_lpMapiSup_参数调用**OpenIMsgOnIStg**函数时, _lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指针是可选的。 
  
因为它处理的是基础 OLE 对象, 所以 MAPI 也需要使用 OLE 内存分配。 有关 ole 结构化存储对象和 ole 内存分配的详细信息, 请参阅_OLE 程序员参考_。 
  
如果为_lpMapiSup_提供了有效值, **IMessage**将通过调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法为 IMAPIProp 提供进度用户界面来支持 MAPI_DIALOG 和 ATTACH_DIALOG 标志[:: CopyTo](imapiprop-copyto.md)和[IMessage::D eleteattach](imessage-deleteattach.md)方法。 此外, [IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法尝试通过调用[IMAPISupport:: OpenAddressBook](imapisupport-openaddressbook.md)方法并对生成的通讯簿对象进行调用, 将短期条目标识符转换为长期条目标识符。 如果为_lpMapiSup_传递了 NULL, **IMessage**将忽略 MAPI_DIALOG 和 ATTACH_DIALOG, 并存储短期条目标识符, 而不进行转换。 
  
_lpStg_参数指向的**IStorage**对象必须以 STGM_READ 或 STGM_READWRITE 模式打开。 如果使用的是 STGM_READWRITE 模式, 还必须设置 STGM_TRANSACTED 模式。 
  
由_lpfMsgCallRelease_参数指向的回调函数是可选的;如果提供, 则它应基于[MSGCALLRELEASE](msgcallrelease.md)函数原型。 当**IMessage**的**IStorage**对象的引用计数由最后一次调用其**Release**方法时, **IMessage**接口将调用它。 回调函数通常用于释放基础**IStorage**接口。 在进行回调之后, **IMessage**将不会尝试访问_lpStg_参数指向的**IStorage**对象。 
  
某些客户端或提供程序可能会在**IStorage**对象中写入其他数据, 而不是调用其[SaveChanges](imapiprop-savechanges.md)方法时**IMessage**本身写入的内容。 在处理**SaveChanges**调用时, 客户端或提供程序可以使用 IMSG_NO_ISTG_COMMIT 标志来阻止**IMessage**调用 OLE **IStorage:: COMMIT**方法;在这种情况下, 在写入其他数据时, 客户端或提供程序必须自己提交**IStorage**对象。 为帮助实现此目的, **IMessage**实现可确保对在**IStorage**对象中创建的所有 substorages 的名称进行命名, 该对象以字符串 "__" 开头, 即带有两个下划线。 通过将其 substorage 名称保留在此命名空间之外, 客户端或提供程序可以避免名称冲突。 
  
MAPI 不会定义对邮件的子网页执行的多个打开操作的行为, 如附件、流或嵌入邮件。 mapi 当前允许打开已经打开的子对象, 但 mapi 通过增加现有 open 对象的引用数并将其返回到调用[IMessage:: OpenAttach 的客户端或提供程序来执行打开操作。](imessage-openattach.md)或[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。 这意味着, 对子方法的第一个 open 操作请求的访问权限是为所有后续打开操作提供的访问权限, 而不考虑这些操作请求的访问权限。 
  
将邮件放入附件的正确过程是使用接口标识符 IID_IMessage 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。 **OpenProperty**目前还支持创建可直接在 OLE **IStorage**接口上使用的邮件附件, 即使用 IID_IStorage 接口标识符。 支持**IStorage**访问, 以便于将 Microsoft Word 文档置于附件中, 而无需将其转换为 OLE IStream 接口或从 OLE **IStream**接口进行转换。 但是, 如果向**OpenIMsgOnIStg**传递了指向附件数据的**IStorage**指针, 然后以错误的顺序发布这些对象, 则**IMessage**可能不会以预期方式运行。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |LoadMSGToMessage  <br/> |MFCMAPI 使用**OpenIMsgOnIStg**方法在上打开 IMessage 接口。MSG 文件, 以便可以使用 MAPI 对文件进行操作。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

