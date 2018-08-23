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
# <a name="openimsgonistg"></a><span data-ttu-id="16832-103">OpenIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="16832-103">OpenIMsgOnIStg</span></span>

<span data-ttu-id="16832-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16832-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16832-105">生成上现有 OLE **IStorage**对象，用于在消息会话中的一个新[IMessage](imessageimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="16832-105">Builds a new [IMessage](imessageimapiprop.md) object on top of an existing OLE **IStorage** object, to be used within a message session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="16832-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="16832-106">Header file:</span></span>  <br/> |<span data-ttu-id="16832-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="16832-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="16832-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="16832-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="16832-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="16832-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="16832-110">调用：</span><span class="sxs-lookup"><span data-stu-id="16832-110">Called by:</span></span>  <br/> |<span data-ttu-id="16832-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="16832-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="16832-112">参数</span><span class="sxs-lookup"><span data-stu-id="16832-112">Parameters</span></span>

<span data-ttu-id="16832-113">_lpMsgSess_</span><span class="sxs-lookup"><span data-stu-id="16832-113">_lpMsgSess_</span></span>
  
> <span data-ttu-id="16832-114">[in]在其中新**IMessage**上**IStorage**对象是要创建的邮件会话对象的指针。</span><span class="sxs-lookup"><span data-stu-id="16832-114">[in] Pointer to a message session object within which the new **IMessage**-on- **IStorage** object is to be created.</span></span> 
    
<span data-ttu-id="16832-115">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="16832-115">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="16832-116">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="16832-116">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
<span data-ttu-id="16832-117">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="16832-117">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="16832-118">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="16832-118">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
<span data-ttu-id="16832-119">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="16832-119">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="16832-120">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="16832-120">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
<span data-ttu-id="16832-121">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="16832-121">_lpMalloc_</span></span>
  
> <span data-ttu-id="16832-122">[in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="16832-122">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="16832-123">**IMessage**接口需要时要使用此分配方法使用如**IStorage**和**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="16832-123">The **IMessage** interface needs to use this allocation method when working with interfaces such as **IStorage** and **IStream**.</span></span> 
    
<span data-ttu-id="16832-124">_lpMapiSup_</span><span class="sxs-lookup"><span data-stu-id="16832-124">_lpMapiSup_</span></span>
  
> <span data-ttu-id="16832-125">[in]对 MAPI 支持对象的服务提供商可以使用调用的方法的可选指针[IMAPISupport: IUnknown](imapisupportiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="16832-125">[in] Optional pointer to a MAPI support object that a service provider can use to call the methods of the [IMAPISupport : IUnknown](imapisupportiunknown.md) interface.</span></span> 
    
<span data-ttu-id="16832-126">_lpStg_</span><span class="sxs-lookup"><span data-stu-id="16832-126">_lpStg_</span></span>
  
> <span data-ttu-id="16832-127">[传入、 传出]指向 OLE **IStorage**对象的处于打开状态，并且具有只读或读/写权限。</span><span class="sxs-lookup"><span data-stu-id="16832-127">[in, out] Pointer to an OLE **IStorage** object that is open and has read-only or read/write permission.</span></span> <span data-ttu-id="16832-128">由于**IMessage**不支持只写访问， **OpenIMsgOnIStg**不接受在只写模式下打开的存储对象。</span><span class="sxs-lookup"><span data-stu-id="16832-128">Because **IMessage** does not support write-only access, **OpenIMsgOnIStg** does not accept a storage object opened in write-only mode.</span></span> 
    
<span data-ttu-id="16832-129">_lpfMsgCallRelease_</span><span class="sxs-lookup"><span data-stu-id="16832-129">_lpfMsgCallRelease_</span></span>
  
> <span data-ttu-id="16832-130">[in]指向基于 MAPI 是**IMessage**上**IStorage**对象上调用以下的上一版本[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数的可选指针。</span><span class="sxs-lookup"><span data-stu-id="16832-130">[in] Optional pointer to a callback function based on the [MSGCALLRELEASE](msgcallrelease.md) prototype that MAPI is to call following the last release on the **IMessage**-on- **IStorage** object.</span></span> 
    
<span data-ttu-id="16832-131">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="16832-131">_ulCallerData_</span></span>
  
> <span data-ttu-id="16832-132">[in]呼叫者数据，与**IMessage**-亮- **IStorage**对象一起保存由 MAPI 并传递给**MSGCALLRELEASE**基于回调函数。</span><span class="sxs-lookup"><span data-stu-id="16832-132">[in] Caller data saved by MAPI with the **IMessage**-on- **IStorage** object and passed to the **MSGCALLRELEASE** based callback function.</span></span> <span data-ttu-id="16832-133">数据提供有关**IMessage**对象正在发布的上下文和在其中生成**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="16832-133">The data provides context about the **IMessage** object being released and the **IStorage** object on top of which it was built.</span></span> 
    
<span data-ttu-id="16832-134">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="16832-134">_ulFlags_</span></span>
  
> <span data-ttu-id="16832-135">[in]用于控制是否在客户端应用程序或服务提供商调用**IMessage::SaveChanges**方法时调用的 OLE **IStorage::Commit**方法的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="16832-135">[in] Bitmask of flags used to control whether the OLE **IStorage::Commit** method is called when the client application or service provider calls the **IMessage::SaveChanges** method.</span></span> <span data-ttu-id="16832-136">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="16832-136">The following flags can be set:</span></span> 
    
<span data-ttu-id="16832-137">IMSG_NO_ISTG_COMMIT</span><span class="sxs-lookup"><span data-stu-id="16832-137">IMSG_NO_ISTG_COMMIT</span></span> 
  
> <span data-ttu-id="16832-138">OLE 方法**IStorage::Commit**不是在客户端或提供程序呼叫[SaveChanges](imapiprop-savechanges.md)时调用。</span><span class="sxs-lookup"><span data-stu-id="16832-138">The OLE method **IStorage::Commit** is not to be called when the client or provider calls [SaveChanges](imapiprop-savechanges.md).</span></span> 
    
<span data-ttu-id="16832-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="16832-139">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="16832-140">允许创建 Unicode.msg 文件。</span><span class="sxs-lookup"><span data-stu-id="16832-140">Enables creation of Unicode .msg files.</span></span> <span data-ttu-id="16832-141">生成的[IMessage](imessageimapiprop.md)文件显示在其[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md) STORE_UNICODE_OK，并支持 Unicode 属性。</span><span class="sxs-lookup"><span data-stu-id="16832-141">The resulting [IMessage](imessageimapiprop.md) file shows STORE_UNICODE_OK in its [PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md) and supports Unicode properties.</span></span> 
    
  > [!NOTE]
  > <span data-ttu-id="16832-142">在此函数在 Outlook 2003 或更高版本中仅支持 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="16832-142">The MAPI_UNICODE flag is only supported in this function on Outlook 2003 or higher.</span></span> 
  
<span data-ttu-id="16832-143">_lppMsg_</span><span class="sxs-lookup"><span data-stu-id="16832-143">_lppMsg_</span></span>
  
> <span data-ttu-id="16832-144">[输出]指向打开**IMessage**对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="16832-144">[out] Pointer to a pointer to the opened **IMessage** object.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="16832-145">返回值</span><span class="sxs-lookup"><span data-stu-id="16832-145">Return value</span></span>

<span data-ttu-id="16832-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="16832-146">S_OK</span></span> 
  
> <span data-ttu-id="16832-147">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="16832-147">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="16832-148">注解</span><span class="sxs-lookup"><span data-stu-id="16832-148">Remarks</span></span>

<span data-ttu-id="16832-149">Property 属性只能在 property 对象，即，实现的对象上访问[IMAPIProp: IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="16832-149">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="16832-150">使 MAPI 属性 OLE 结构化的存储对象上可用， **OpenIMsgOnIStg**生成[IMessage: IMAPIProp](imessageimapiprop.md) OLE **IStorage**对象上的对象。</span><span class="sxs-lookup"><span data-stu-id="16832-150">To make MAPI properties available on an OLE structured storage object, **OpenIMsgOnIStg** builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="16832-151">此类对象上的属性属性可以设置或更改与[SetAttribIMsgOnIStg](setattribimsgonistg.md)和检索与[GetAttribIMsgOnIStg](getattribimsgonistg.md)。</span><span class="sxs-lookup"><span data-stu-id="16832-151">The property attributes on such objects can be set or altered with [SetAttribIMsgOnIStg](setattribimsgonistg.md) and retrieved with [GetAttribIMsgOnIStg](getattribimsgonistg.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="16832-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="16832-152">Notes to callers</span></span>

<span data-ttu-id="16832-153">调用**OpenIMsgOnIStg**之前，应使用[OpenIMsgSession](openimsgsession.md)打开的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="16832-153">A message session should be opened with [OpenIMsgSession](openimsgsession.md) before **OpenIMsgOnIStg** is called.</span></span> <span data-ttu-id="16832-154">提供一个有效_lpMsgSess_参数使 sures 该新邮件创建消息会话中，以便当关闭会话关闭它。</span><span class="sxs-lookup"><span data-stu-id="16832-154">Supplying a valid  _lpMsgSess_ parameter make sures that the new message is created within a message session so that it is closed when the session is closed.</span></span> <span data-ttu-id="16832-155">如果_lpMsgSess_为 NULL，则独立于任何邮件会话创建消息。</span><span class="sxs-lookup"><span data-stu-id="16832-155">If  _lpMsgSess_ is NULL, the message is created independently of any message session.</span></span> <span data-ttu-id="16832-156">如果客户端应用程序或服务提供程序创建邮件没有版本以及所有附件并打开表，内存被泄露，可能导致应用程序终止。</span><span class="sxs-lookup"><span data-stu-id="16832-156">If the client application or service provider that created the message does not release it, as well as all its attachments and open tables, memory is leaked and may cause the application to terminate.</span></span> 
  
<span data-ttu-id="16832-157">MAPI 使用所指的_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口时的功能如[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="16832-157">MAPI uses the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="16832-158">使用有效_lpMapiSup_参数调用**OpenIMsgOnIStg**函数时， _lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指针是可选的。</span><span class="sxs-lookup"><span data-stu-id="16832-158">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ pointers are optional when the **OpenIMsgOnIStg** function is called with a valid  _lpMapiSup_ parameter.</span></span> 
  
<span data-ttu-id="16832-159">因为它处理基础 OLE 对象，MAPI 还需要使用 OLE 内存分配。</span><span class="sxs-lookup"><span data-stu-id="16832-159">Because it is dealing with an underlying OLE object, MAPI also needs to use OLE memory allocation.</span></span> <span data-ttu-id="16832-160">有关存储的结构化的 OLE 对象和 OLE 内存分配的详细信息，请参阅_OLE 程序员参考_。</span><span class="sxs-lookup"><span data-stu-id="16832-160">For more information about OLE structured storage objects and OLE memory allocation, see the  _OLE Programmer's Reference_.</span></span> 
  
<span data-ttu-id="16832-161">如果为_lpMapiSup_提供一个有效的值， **IMessage**通过调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法可提供给[IMAPIProp::CopyTo](imapiprop-copyto.md)的进度用户界面支持的 MAPI_DIALOG 和 ATTACH_DIALOG 标志和[IMessage::DeleteAttach](imessage-deleteattach.md)方法。</span><span class="sxs-lookup"><span data-stu-id="16832-161">If a valid value is supplied for  _lpMapiSup_, **IMessage** supports the MAPI_DIALOG and ATTACH_DIALOG flags by calling the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to supply a progress user interface for the [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMessage::DeleteAttach](imessage-deleteattach.md) methods.</span></span> <span data-ttu-id="16832-162">此外， [IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法将转换为长期条目标识符短期条目标识符，通过调用[IMAPISupport::OpenAddressBook](imapisupport-openaddressbook.md)方法并生成的通讯簿对象上进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="16832-162">Also, the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method attempts to convert short-term entry identifiers to long-term entry identifiers by calling the [IMAPISupport::OpenAddressBook](imapisupport-openaddressbook.md) method and making calls on the resulting address book object.</span></span> <span data-ttu-id="16832-163">如果为_lpMapiSup_传递 NULL，则**IMessage**忽略 MAPI_DIALOG 和 ATTACH_DIALOG，并将存储不需转换的短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="16832-163">If NULL is passed for  _lpMapiSup_, **IMessage** ignores MAPI_DIALOG and ATTACH_DIALOG and stores short-term entry identifiers without conversion.</span></span> 
  
<span data-ttu-id="16832-164">必须在 STGM_READ 或 STGM_READWRITE 模式下打开_lpStg_参数指向**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="16832-164">The **IStorage** object pointed to by the  _lpStg_ parameter must be opened in either the STGM_READ or STGM_READWRITE mode.</span></span> <span data-ttu-id="16832-165">如果使用的 STGM_READWRITE 模式，则还必须设置 STGM_TRANSACTED 模式。</span><span class="sxs-lookup"><span data-stu-id="16832-165">If the STGM_READWRITE mode is used, the STGM_TRANSACTED mode must also be set.</span></span> 
  
<span data-ttu-id="16832-166">_LpfMsgCallRelease_参数指向的回调函数是可选的;如果提供，它应基于[MSGCALLRELEASE](msgcallrelease.md)函数原型。</span><span class="sxs-lookup"><span data-stu-id="16832-166">The callback function pointed to by the  _lpfMsgCallRelease_ parameter is optional; if provided, it should be based on the [MSGCALLRELEASE](msgcallrelease.md) function prototype.</span></span> <span data-ttu-id="16832-167">**IMessage**接口调用它时**IMessage**-亮- **IStorage**对象的引用数设置为零通过其**版本**方法的最后一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="16832-167">The **IMessage** interface calls it when the reference count of the **IMessage**-on- **IStorage** object is set to zero by the last call to its **Release** method.</span></span> <span data-ttu-id="16832-168">回调函数常用以释放基础**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="16832-168">The callback function is commonly used to free the underlying **IStorage** interface.</span></span> <span data-ttu-id="16832-169">**IMessage**才会尝试访问进行回调后_lpStg_参数指向的**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="16832-169">**IMessage** will not attempt to access the **IStorage** object pointed to by the  _lpStg_ parameter after making the callback.</span></span> 
  
<span data-ttu-id="16832-170">某些客户端或提供程序可能会写入其他数据向超出哪些**IMessage** **IStorage**对象本身写入调用其[SaveChanges](imapiprop-savechanges.md)方法时。</span><span class="sxs-lookup"><span data-stu-id="16832-170">Some clients or providers might write additional data to the **IStorage** object beyond what **IMessage** itself writes when its [SaveChanges](imapiprop-savechanges.md) method is called.</span></span> <span data-ttu-id="16832-171">在客户端或提供程序可以使用 IMSG_NO_ISTG_COMMIT 标志防止**IMessage**处理**SaveChanges**呼叫; 时调用的 OLE **IStorage::Commit**方法在这种情况下在客户端或提供程序必须本身提交**IStorage**对象时写入的其他数据。</span><span class="sxs-lookup"><span data-stu-id="16832-171">The client or provider can use the IMSG_NO_ISTG_COMMIT flag to prevent **IMessage** from calling the OLE **IStorage::Commit** method while processing a **SaveChanges** call; in this case the client or provider must itself commit the **IStorage** object when the additional data is written.</span></span> <span data-ttu-id="16832-172">若要在此帮助， **IMessage**实现保证命名它与两个下划线，即开头的字符串"__" **IStorage**对象中创建的所有 substorages。</span><span class="sxs-lookup"><span data-stu-id="16832-172">To aid in this, the **IMessage** implementation guarantees to name all substorages it creates in the **IStorage** object starting with the string "__", that is, with two underscores.</span></span> <span data-ttu-id="16832-173">在客户端或提供程序可以通过保留此命名空间不足及其子存储名称避免名称冲突。</span><span class="sxs-lookup"><span data-stu-id="16832-173">The client or provider can avoid name collisions by keeping its substorage names out of this namespace.</span></span> 
  
<span data-ttu-id="16832-174">MAPI 不定义多个打开的操作执行上一条消息，如附件、 流或嵌入的邮件的子对象的行为。</span><span class="sxs-lookup"><span data-stu-id="16832-174">MAPI does not define the behavior of multiple open operations performed on a subobject of a message, such as an attachment, a stream, or an embedded message.</span></span> <span data-ttu-id="16832-175">MAPI 当前允许已经打开多，一次打开的子对象，但 MAPI 通过递增打开现有的对象的引用计数和返回到客户端或提供程序调用[IMessage::OpenAttach 执行打开操作](imessage-openattach.md)或[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="16832-175">MAPI currently allows a subobject that is already open to be opened once more, but MAPI performs the open operation by incrementing the reference count for the existing open object and returning it to the client or provider that called the [IMessage::OpenAttach](imessage-openattach.md) or [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method.</span></span> <span data-ttu-id="16832-176">这意味着请求的子对象上的第一个打开操作的访问提供对于所有后续打开操作，而不考虑请求的操作的访问的访问权限。</span><span class="sxs-lookup"><span data-stu-id="16832-176">This means the access requested for the first open operation on a subobject is the access provided for all subsequent open operations, regardless of the access requested by the operations.</span></span> 
  
<span data-ttu-id="16832-177">将一条消息放入附件到正确的步骤是调用带有接口标识符的 IID_IMessage [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="16832-177">The correct procedure for placing a message into an attachment is to call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with an interface identifier of IID_IMessage.</span></span> <span data-ttu-id="16832-178">**OpenProperty**当前还支持创建可用的邮件附件的直接在 OLE **IStorage**界面上，即，使用 IID_IStorage 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="16832-178">**OpenProperty** currently also supports creation of message attachments available directly on the OLE **IStorage** interface, that is, using the IID_IStorage interface identifier.</span></span> <span data-ttu-id="16832-179">支持**IStorage**访问允许不将其转换为或从 OLE **IStream**接口置于附件 Microsoft Word 文档的简便方法。</span><span class="sxs-lookup"><span data-stu-id="16832-179">**IStorage** access is supported to allow an easy way to put a Microsoft Word document into an attachment without converting it to or from the OLE **IStream** interface.</span></span> <span data-ttu-id="16832-180">但是，如果**OpenIMsgOnIStg**传递给附件数据**IStorage**指针和顺序不正确释放对象然后**IMessage**可能不预知行为。</span><span class="sxs-lookup"><span data-stu-id="16832-180">However, **IMessage** may not behave predictably if **OpenIMsgOnIStg** is passed an **IStorage** pointer to the attachment data and then the objects are released in the wrong order.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="16832-181">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="16832-181">MFCMAPI reference</span></span>

<span data-ttu-id="16832-182">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="16832-182">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="16832-183">**文件**</span><span class="sxs-lookup"><span data-stu-id="16832-183">**File**</span></span>|<span data-ttu-id="16832-184">**函数**</span><span class="sxs-lookup"><span data-stu-id="16832-184">**Function**</span></span>|<span data-ttu-id="16832-185">**Comment**</span><span class="sxs-lookup"><span data-stu-id="16832-185">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16832-186">File.cpp</span><span class="sxs-lookup"><span data-stu-id="16832-186">File.cpp</span></span>  <br/> |<span data-ttu-id="16832-187">LoadMSGToMessage</span><span class="sxs-lookup"><span data-stu-id="16832-187">LoadMSGToMessage</span></span>  <br/> |<span data-ttu-id="16832-188">MFCMAPI 使用**OpenIMsgOnIStg**方法打开 IMessage 接口的顶部。MSG 文件，以便可能与 MAPI 操纵文件。</span><span class="sxs-lookup"><span data-stu-id="16832-188">MFCMAPI uses the **OpenIMsgOnIStg** method to open an IMessage interface on top of the .MSG file so that the file may be manipulated with MAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="16832-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16832-189">See also</span></span>

- [<span data-ttu-id="16832-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="16832-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

