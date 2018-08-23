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
ms.openlocfilehash: 56e663ced33da933b4276911b609f2fae1c5d78e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563961"
---
# <a name="openimsgonistg"></a>OpenIMsgOnIStg

**适用于**： Outlook 2013 |Outlook 2016 
  
生成上现有 OLE **IStorage**对象，用于在消息会话中的一个新[IMessage](imessageimapiprop.md)对象。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]在其中新**IMessage**上**IStorage**对象是要创建的邮件会话对象的指针。 
    
_lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
_lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。 
    
_lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
_lpMalloc_
  
> [in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。 **IMessage**接口需要时要使用此分配方法使用如**IStorage**和**IStream**接口。 
    
_lpMapiSup_
  
> [in]对 MAPI 支持对象的服务提供商可以使用调用的方法的可选指针[IMAPISupport: IUnknown](imapisupportiunknown.md)接口。 
    
_lpStg_
  
> [传入、 传出]指向 OLE **IStorage**对象的处于打开状态，并且具有只读或读/写权限。 由于**IMessage**不支持只写访问， **OpenIMsgOnIStg**不接受在只写模式下打开的存储对象。 
    
_lpfMsgCallRelease_
  
> [in]指向基于 MAPI 是**IMessage**上**IStorage**对象上调用以下的上一版本[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数的可选指针。 
    
_ulCallerData_
  
> [in]呼叫者数据，与**IMessage**-亮- **IStorage**对象一起保存由 MAPI 并传递给**MSGCALLRELEASE**基于回调函数。 数据提供有关**IMessage**对象正在发布的上下文和在其中生成**IStorage**对象。 
    
_ulFlags_
  
> [in]用于控制是否在客户端应用程序或服务提供商调用**IMessage::SaveChanges**方法时调用的 OLE **IStorage::Commit**方法的标志的位掩码。 可以设置以下标志： 
    
IMSG_NO_ISTG_COMMIT 
  
> OLE 方法**IStorage::Commit**不是在客户端或提供程序呼叫[SaveChanges](imapiprop-savechanges.md)时调用。 
    
MAPI_UNICODE
  
> 允许创建 Unicode.msg 文件。 生成的[IMessage](imessageimapiprop.md)文件显示在其[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md) STORE_UNICODE_OK，并支持 Unicode 属性。 
    
  > [!NOTE]
  > 在此函数在 Outlook 2003 或更高版本中仅支持 MAPI_UNICODE 标志。 
  
_lppMsg_
  
> [输出]指向打开**IMessage**对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 使 MAPI 属性 OLE 结构化的存储对象上可用， **OpenIMsgOnIStg**生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。 此类对象上的属性属性可以设置或更改与[SetAttribIMsgOnIStg](setattribimsgonistg.md)和检索与[GetAttribIMsgOnIStg](getattribimsgonistg.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**OpenIMsgOnIStg**之前，应使用[OpenIMsgSession](openimsgsession.md)打开的邮件会话。 提供一个有效_lpMsgSess_参数使 sures 该新邮件创建消息会话中，以便当关闭会话关闭它。 如果_lpMsgSess_为 NULL，则独立于任何邮件会话创建消息。 如果客户端应用程序或服务提供程序创建邮件没有版本以及所有附件并打开表，内存被泄露，可能导致应用程序终止。 
  
MAPI 使用所指的_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口时的功能如[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。 使用有效_lpMapiSup_参数调用**OpenIMsgOnIStg**函数时， _lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指针是可选的。 
  
因为它处理基础 OLE 对象，MAPI 还需要使用 OLE 内存分配。 有关存储的结构化的 OLE 对象和 OLE 内存分配的详细信息，请参阅_OLE 程序员参考_。 
  
如果为_lpMapiSup_提供一个有效的值， **IMessage**通过调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法可提供给[IMAPIProp::CopyTo](imapiprop-copyto.md)的进度用户界面支持的 MAPI_DIALOG 和 ATTACH_DIALOG 标志和[IMessage::DeleteAttach](imessage-deleteattach.md)方法。 此外， [IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法将转换为长期条目标识符短期条目标识符，通过调用[IMAPISupport::OpenAddressBook](imapisupport-openaddressbook.md)方法并生成的通讯簿对象上进行呼叫。 如果为_lpMapiSup_传递 NULL，则**IMessage**忽略 MAPI_DIALOG 和 ATTACH_DIALOG，并将存储不需转换的短期条目标识符。 
  
必须在 STGM_READ 或 STGM_READWRITE 模式下打开_lpStg_参数指向**IStorage**对象。 如果使用的 STGM_READWRITE 模式，则还必须设置 STGM_TRANSACTED 模式。 
  
_LpfMsgCallRelease_参数指向的回调函数是可选的;如果提供，它应基于[MSGCALLRELEASE](msgcallrelease.md)函数原型。 **IMessage**接口调用它时**IMessage**-亮- **IStorage**对象的引用数设置为零通过其**版本**方法的最后一个呼叫。 回调函数常用以释放基础**IStorage**接口。 **IMessage**才会尝试访问进行回调后_lpStg_参数指向的**IStorage**对象。 
  
某些客户端或提供程序可能会写入其他数据向超出哪些**IMessage** **IStorage**对象本身写入调用其[SaveChanges](imapiprop-savechanges.md)方法时。 在客户端或提供程序可以使用 IMSG_NO_ISTG_COMMIT 标志防止**IMessage**处理**SaveChanges**呼叫; 时调用的 OLE **IStorage::Commit**方法在这种情况下在客户端或提供程序必须本身提交**IStorage**对象时写入的其他数据。 若要在此帮助， **IMessage**实现保证命名它与两个下划线，即开头的字符串"__" **IStorage**对象中创建的所有 substorages。 在客户端或提供程序可以通过保留此命名空间不足及其子存储名称避免名称冲突。 
  
MAPI 不定义多个打开的操作执行上一条消息，如附件、 流或嵌入的邮件的子对象的行为。 MAPI 当前允许已经打开多，一次打开的子对象，但 MAPI 通过递增打开现有的对象的引用计数和返回到客户端或提供程序调用[IMessage::OpenAttach 执行打开操作](imessage-openattach.md)或[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 这意味着请求的子对象上的第一个打开操作的访问提供对于所有后续打开操作，而不考虑请求的操作的访问的访问权限。 
  
将一条消息放入附件到正确的步骤是调用带有接口标识符的 IID_IMessage [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 **OpenProperty**当前还支持创建可用的邮件附件的直接在 OLE **IStorage**界面上，即，使用 IID_IStorage 接口标识符。 支持**IStorage**访问允许不将其转换为或从 OLE **IStream**接口置于附件 Microsoft Word 文档的简便方法。 但是，如果**OpenIMsgOnIStg**传递给附件数据**IStorage**指针和顺序不正确释放对象然后**IMessage**可能不预知行为。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|File.cpp  <br/> |LoadMSGToMessage  <br/> |MFCMAPI 使用**OpenIMsgOnIStg**方法打开 IMessage 接口的顶部。MSG 文件，以便可能与 MAPI 操纵文件。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

