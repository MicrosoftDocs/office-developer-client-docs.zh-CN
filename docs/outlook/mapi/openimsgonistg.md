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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348613"
---
# <a name="openimsgonistg"></a><span data-ttu-id="3cdc8-103">OpenIMsgOnIStg</span><span class="sxs-lookup"><span data-stu-id="3cdc8-103">OpenIMsgOnIStg</span></span>

<span data-ttu-id="3cdc8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3cdc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3cdc8-105">在现有 OLE **IStorage**对象的顶部生成一个新的[IMessage](imessageimapiprop.md)对象, 以在邮件会话中使用。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-105">Builds a new [IMessage](imessageimapiprop.md) object on top of an existing OLE **IStorage** object, to be used within a message session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3cdc8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3cdc8-106">Header file:</span></span>  <br/> |<span data-ttu-id="3cdc8-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="3cdc8-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="3cdc8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="3cdc8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3cdc8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3cdc8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3cdc8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="3cdc8-110">Called by:</span></span>  <br/> |<span data-ttu-id="3cdc8-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="3cdc8-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="3cdc8-112">参数</span><span class="sxs-lookup"><span data-stu-id="3cdc8-112">Parameters</span></span>

<span data-ttu-id="3cdc8-113">_lpMsgSess_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-113">_lpMsgSess_</span></span>
  
> <span data-ttu-id="3cdc8-114">实时指向要在其中创建新的**IMessage** **IStorage**对象的邮件会话对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-114">[in] Pointer to a message session object within which the new **IMessage**-on- **IStorage** object is to be created.</span></span> 
    
<span data-ttu-id="3cdc8-115">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-115">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="3cdc8-116">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-116">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
<span data-ttu-id="3cdc8-117">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-117">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="3cdc8-118">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-118">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
<span data-ttu-id="3cdc8-119">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-119">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="3cdc8-120">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-120">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
<span data-ttu-id="3cdc8-121">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-121">_lpMalloc_</span></span>
  
> <span data-ttu-id="3cdc8-122">实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-122">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="3cdc8-123">在使用**IStorage**和**IStream**等接口时, **IMessage**接口需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-123">The **IMessage** interface needs to use this allocation method when working with interfaces such as **IStorage** and **IStream**.</span></span> 
    
<span data-ttu-id="3cdc8-124">_lpMapiSup_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-124">_lpMapiSup_</span></span>
  
> <span data-ttu-id="3cdc8-125">实时指向 MAPI 支持对象的可选指针, 服务提供程序可以使用该指针调用[IMAPISupport: IUnknown](imapisupportiunknown.md)接口的方法。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-125">[in] Optional pointer to a MAPI support object that a service provider can use to call the methods of the [IMAPISupport : IUnknown](imapisupportiunknown.md) interface.</span></span> 
    
<span data-ttu-id="3cdc8-126">_lpStg_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-126">_lpStg_</span></span>
  
> <span data-ttu-id="3cdc8-127">[in, out]指向打开且具有只读或读/写权限的 OLE **IStorage**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-127">[in, out] Pointer to an OLE **IStorage** object that is open and has read-only or read/write permission.</span></span> <span data-ttu-id="3cdc8-128">由于**IMessage**不支持只写访问, 因此**OpenIMsgOnIStg**不接受以只写模式打开的存储对象。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-128">Because **IMessage** does not support write-only access, **OpenIMsgOnIStg** does not accept a storage object opened in write-only mode.</span></span> 
    
<span data-ttu-id="3cdc8-129">_lpfMsgCallRelease_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-129">_lpfMsgCallRelease_</span></span>
  
> <span data-ttu-id="3cdc8-130">实时指向基于[MSGCALLRELEASE](msgcallrelease.md)原型的回调函数的可选指针, 该函数是 MAPI 在**IMessage**对象上的最后一个版本之后调用的\*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-130">[in] Optional pointer to a callback function based on the [MSGCALLRELEASE](msgcallrelease.md) prototype that MAPI is to call following the last release on the **IMessage**-on- **IStorage** object.</span></span> 
    
<span data-ttu-id="3cdc8-131">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-131">_ulCallerData_</span></span>
  
> <span data-ttu-id="3cdc8-132">实时MAPI 使用**IMessage**- **IStorage**对象保存的调用方数据, 并传递给基于**MSGCALLRELEASE**的回调函数。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-132">[in] Caller data saved by MAPI with the **IMessage**-on- **IStorage** object and passed to the **MSGCALLRELEASE** based callback function.</span></span> <span data-ttu-id="3cdc8-133">数据提供有关要释放的**IMessage**对象的上下文以及在其上生成该对象的**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-133">The data provides context about the **IMessage** object being released and the **IStorage** object on top of which it was built.</span></span> 
    
<span data-ttu-id="3cdc8-134">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-134">_ulFlags_</span></span>
  
> <span data-ttu-id="3cdc8-135">实时用于控制是否在客户端应用程序或服务提供程序调用**IMessage:: SaveChanges**方法时调用 OLE **IStorage:: Commit**方法的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-135">[in] Bitmask of flags used to control whether the OLE **IStorage::Commit** method is called when the client application or service provider calls the **IMessage::SaveChanges** method.</span></span> <span data-ttu-id="3cdc8-136">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="3cdc8-136">The following flags can be set:</span></span> 
    
<span data-ttu-id="3cdc8-137">IMSG_NO_ISTG_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3cdc8-137">IMSG_NO_ISTG_COMMIT</span></span> 
  
> <span data-ttu-id="3cdc8-138">在客户端或提供程序调用[SaveChanges](imapiprop-savechanges.md)时, 不会调用 OLE 方法**IStorage:: Commit** 。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-138">The OLE method **IStorage::Commit** is not to be called when the client or provider calls [SaveChanges](imapiprop-savechanges.md).</span></span> 
    
<span data-ttu-id="3cdc8-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3cdc8-139">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="3cdc8-140">允许创建 Unicode .msg 文件。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-140">Enables creation of Unicode .msg files.</span></span> <span data-ttu-id="3cdc8-141">生成的[IMessage](imessageimapiprop.md)文件在其[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)中显示 STORE_UNICODE_OK, 并支持 UNICODE 属性。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-141">The resulting [IMessage](imessageimapiprop.md) file shows STORE_UNICODE_OK in its [PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md) and supports Unicode properties.</span></span> 
    
  > [!NOTE]
  > <span data-ttu-id="3cdc8-142">仅在 Outlook 2003 或更高版本的此函数中支持 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-142">The MAPI_UNICODE flag is only supported in this function on Outlook 2003 or higher.</span></span> 
  
<span data-ttu-id="3cdc8-143">_lppMsg_</span><span class="sxs-lookup"><span data-stu-id="3cdc8-143">_lppMsg_</span></span>
  
> <span data-ttu-id="3cdc8-144">排除指向打开的**IMessage**对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-144">[out] Pointer to a pointer to the opened **IMessage** object.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3cdc8-145">返回值</span><span class="sxs-lookup"><span data-stu-id="3cdc8-145">Return value</span></span>

<span data-ttu-id="3cdc8-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cdc8-146">S_OK</span></span> 
  
> <span data-ttu-id="3cdc8-147">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-147">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3cdc8-148">注解</span><span class="sxs-lookup"><span data-stu-id="3cdc8-148">Remarks</span></span>

<span data-ttu-id="3cdc8-149">只能在属性对象 (即实现[IMAPIProp: IUnknown](imapipropiunknown.md)接口的对象) 上访问属性属性。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-149">Property attributes can only be accessed on property objects, that is, objects implementing the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="3cdc8-150">若要使 MAPI 属性在 ole 结构化存储对象上可用, **OpenIMsgOnIStg**在 ole **IStorage**对象的顶部生成[IMessage: IMAPIProp](imessageimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-150">To make MAPI properties available on an OLE structured storage object, **OpenIMsgOnIStg** builds an [IMessage : IMAPIProp](imessageimapiprop.md) object on top of the OLE **IStorage** object.</span></span> <span data-ttu-id="3cdc8-151">此类对象上的属性属性可以使用[SetAttribIMsgOnIStg](setattribimsgonistg.md)进行设置或更改, 并可使用[GetAttribIMsgOnIStg](getattribimsgonistg.md)进行检索。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-151">The property attributes on such objects can be set or altered with [SetAttribIMsgOnIStg](setattribimsgonistg.md) and retrieved with [GetAttribIMsgOnIStg](getattribimsgonistg.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3cdc8-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3cdc8-152">Notes to callers</span></span>

<span data-ttu-id="3cdc8-153">在调用**OpenIMsgOnIStg**之前, 应使用[OpenIMsgSession](openimsgsession.md)打开一个邮件会话。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-153">A message session should be opened with [OpenIMsgSession](openimsgsession.md) before **OpenIMsgOnIStg** is called.</span></span> <span data-ttu-id="3cdc8-154">提供有效的_lpMsgSess_参数使 sures 能够在邮件会话中创建新邮件, 以便在会话关闭时将其关闭。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-154">Supplying a valid  _lpMsgSess_ parameter make sures that the new message is created within a message session so that it is closed when the session is closed.</span></span> <span data-ttu-id="3cdc8-155">如果_lpMsgSess_为 NULL, 则不会独立于任何邮件会话创建邮件。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-155">If  _lpMsgSess_ is NULL, the message is created independently of any message session.</span></span> <span data-ttu-id="3cdc8-156">如果创建该邮件的客户端应用程序或服务提供程序不释放它以及它的所有附件和打开的表, 则内存泄漏, 并可能导致应用程序终止。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-156">If the client application or service provider that created the message does not release it, as well as all its attachments and open tables, memory is leaked and may cause the application to terminate.</span></span> 
  
<span data-ttu-id="3cdc8-157">MAPI 将_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数用于大多数内存分配和释放, 尤其是在调用对象接口时分配内存供客户端应用程序使用。例如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-157">MAPI uses the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="3cdc8-158">使用有效的_lpMapiSup_参数调用**OpenIMsgOnIStg**函数时, _lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指针是可选的。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-158">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ pointers are optional when the **OpenIMsgOnIStg** function is called with a valid  _lpMapiSup_ parameter.</span></span> 
  
<span data-ttu-id="3cdc8-159">因为它处理的是基础 OLE 对象, 所以 MAPI 也需要使用 OLE 内存分配。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-159">Because it is dealing with an underlying OLE object, MAPI also needs to use OLE memory allocation.</span></span> <span data-ttu-id="3cdc8-160">有关 ole 结构化存储对象和 ole 内存分配的详细信息, 请参阅_OLE 程序员参考_。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-160">For more information about OLE structured storage objects and OLE memory allocation, see the  _OLE Programmer's Reference_.</span></span> 
  
<span data-ttu-id="3cdc8-161">如果为_lpMapiSup_提供了有效值, **IMessage**将通过调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法为 IMAPIProp 提供进度用户界面来支持 MAPI_DIALOG 和 ATTACH_DIALOG 标志[:: CopyTo](imapiprop-copyto.md)和[IMessage::D eleteattach](imessage-deleteattach.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-161">If a valid value is supplied for  _lpMapiSup_, **IMessage** supports the MAPI_DIALOG and ATTACH_DIALOG flags by calling the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to supply a progress user interface for the [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMessage::DeleteAttach](imessage-deleteattach.md) methods.</span></span> <span data-ttu-id="3cdc8-162">此外, [IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法尝试通过调用[IMAPISupport:: OpenAddressBook](imapisupport-openaddressbook.md)方法并对生成的通讯簿对象进行调用, 将短期条目标识符转换为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-162">Also, the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method attempts to convert short-term entry identifiers to long-term entry identifiers by calling the [IMAPISupport::OpenAddressBook](imapisupport-openaddressbook.md) method and making calls on the resulting address book object.</span></span> <span data-ttu-id="3cdc8-163">如果为_lpMapiSup_传递了 NULL, **IMessage**将忽略 MAPI_DIALOG 和 ATTACH_DIALOG, 并存储短期条目标识符, 而不进行转换。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-163">If NULL is passed for  _lpMapiSup_, **IMessage** ignores MAPI_DIALOG and ATTACH_DIALOG and stores short-term entry identifiers without conversion.</span></span> 
  
<span data-ttu-id="3cdc8-164">_lpStg_参数指向的**IStorage**对象必须以 STGM_READ 或 STGM_READWRITE 模式打开。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-164">The **IStorage** object pointed to by the  _lpStg_ parameter must be opened in either the STGM_READ or STGM_READWRITE mode.</span></span> <span data-ttu-id="3cdc8-165">如果使用的是 STGM_READWRITE 模式, 还必须设置 STGM_TRANSACTED 模式。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-165">If the STGM_READWRITE mode is used, the STGM_TRANSACTED mode must also be set.</span></span> 
  
<span data-ttu-id="3cdc8-166">由_lpfMsgCallRelease_参数指向的回调函数是可选的;如果提供, 则它应基于[MSGCALLRELEASE](msgcallrelease.md)函数原型。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-166">The callback function pointed to by the  _lpfMsgCallRelease_ parameter is optional; if provided, it should be based on the [MSGCALLRELEASE](msgcallrelease.md) function prototype.</span></span> <span data-ttu-id="3cdc8-167">当**IMessage**的**IStorage**对象的引用计数由最后一次调用其**Release**方法时, **IMessage**接口将调用它。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-167">The **IMessage** interface calls it when the reference count of the **IMessage**-on- **IStorage** object is set to zero by the last call to its **Release** method.</span></span> <span data-ttu-id="3cdc8-168">回调函数通常用于释放基础**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-168">The callback function is commonly used to free the underlying **IStorage** interface.</span></span> <span data-ttu-id="3cdc8-169">在进行回调之后, **IMessage**将不会尝试访问_lpStg_参数指向的**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-169">**IMessage** will not attempt to access the **IStorage** object pointed to by the  _lpStg_ parameter after making the callback.</span></span> 
  
<span data-ttu-id="3cdc8-170">某些客户端或提供程序可能会在**IStorage**对象中写入其他数据, 而不是调用其[SaveChanges](imapiprop-savechanges.md)方法时**IMessage**本身写入的内容。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-170">Some clients or providers might write additional data to the **IStorage** object beyond what **IMessage** itself writes when its [SaveChanges](imapiprop-savechanges.md) method is called.</span></span> <span data-ttu-id="3cdc8-171">在处理**SaveChanges**调用时, 客户端或提供程序可以使用 IMSG_NO_ISTG_COMMIT 标志来阻止**IMessage**调用 OLE **IStorage:: COMMIT**方法;在这种情况下, 在写入其他数据时, 客户端或提供程序必须自己提交**IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-171">The client or provider can use the IMSG_NO_ISTG_COMMIT flag to prevent **IMessage** from calling the OLE **IStorage::Commit** method while processing a **SaveChanges** call; in this case the client or provider must itself commit the **IStorage** object when the additional data is written.</span></span> <span data-ttu-id="3cdc8-172">为帮助实现此目的, **IMessage**实现可确保对在**IStorage**对象中创建的所有 substorages 的名称进行命名, 该对象以字符串 "__" 开头, 即带有两个下划线。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-172">To aid in this, the **IMessage** implementation guarantees to name all substorages it creates in the **IStorage** object starting with the string "__", that is, with two underscores.</span></span> <span data-ttu-id="3cdc8-173">通过将其 substorage 名称保留在此命名空间之外, 客户端或提供程序可以避免名称冲突。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-173">The client or provider can avoid name collisions by keeping its substorage names out of this namespace.</span></span> 
  
<span data-ttu-id="3cdc8-174">MAPI 不会定义对邮件的子网页执行的多个打开操作的行为, 如附件、流或嵌入邮件。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-174">MAPI does not define the behavior of multiple open operations performed on a subobject of a message, such as an attachment, a stream, or an embedded message.</span></span> <span data-ttu-id="3cdc8-175">mapi 当前允许打开已经打开的子对象, 但 mapi 通过增加现有 open 对象的引用数并将其返回到调用[IMessage:: OpenAttach 的客户端或提供程序来执行打开操作。](imessage-openattach.md)或[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-175">MAPI currently allows a subobject that is already open to be opened once more, but MAPI performs the open operation by incrementing the reference count for the existing open object and returning it to the client or provider that called the [IMessage::OpenAttach](imessage-openattach.md) or [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method.</span></span> <span data-ttu-id="3cdc8-176">这意味着, 对子方法的第一个 open 操作请求的访问权限是为所有后续打开操作提供的访问权限, 而不考虑这些操作请求的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-176">This means the access requested for the first open operation on a subobject is the access provided for all subsequent open operations, regardless of the access requested by the operations.</span></span> 
  
<span data-ttu-id="3cdc8-177">将邮件放入附件的正确过程是使用接口标识符 IID_IMessage 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-177">The correct procedure for placing a message into an attachment is to call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with an interface identifier of IID_IMessage.</span></span> <span data-ttu-id="3cdc8-178">**OpenProperty**目前还支持创建可直接在 OLE **IStorage**接口上使用的邮件附件, 即使用 IID_IStorage 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-178">**OpenProperty** currently also supports creation of message attachments available directly on the OLE **IStorage** interface, that is, using the IID_IStorage interface identifier.</span></span> <span data-ttu-id="3cdc8-179">支持**IStorage**访问, 以便于将 Microsoft Word 文档置于附件中, 而无需将其转换为 OLE IStream 接口或从 OLE **IStream**接口进行转换。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-179">**IStorage** access is supported to allow an easy way to put a Microsoft Word document into an attachment without converting it to or from the OLE **IStream** interface.</span></span> <span data-ttu-id="3cdc8-180">但是, 如果向**OpenIMsgOnIStg**传递了指向附件数据的**IStorage**指针, 然后以错误的顺序发布这些对象, 则**IMessage**可能不会以预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-180">However, **IMessage** may not behave predictably if **OpenIMsgOnIStg** is passed an **IStorage** pointer to the attachment data and then the objects are released in the wrong order.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3cdc8-181">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3cdc8-181">MFCMAPI reference</span></span>

<span data-ttu-id="3cdc8-182">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-182">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3cdc8-183">**文件**</span><span class="sxs-lookup"><span data-stu-id="3cdc8-183">**File**</span></span>|<span data-ttu-id="3cdc8-184">**函数**</span><span class="sxs-lookup"><span data-stu-id="3cdc8-184">**Function**</span></span>|<span data-ttu-id="3cdc8-185">**备注**</span><span class="sxs-lookup"><span data-stu-id="3cdc8-185">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3cdc8-186">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="3cdc8-186">File.cpp</span></span>  <br/> |<span data-ttu-id="3cdc8-187">LoadMSGToMessage</span><span class="sxs-lookup"><span data-stu-id="3cdc8-187">LoadMSGToMessage</span></span>  <br/> |<span data-ttu-id="3cdc8-188">MFCMAPI 使用**OpenIMsgOnIStg**方法在上打开 IMessage 接口。MSG 文件, 以便可以使用 MAPI 对文件进行操作。</span><span class="sxs-lookup"><span data-stu-id="3cdc8-188">MFCMAPI uses the **OpenIMsgOnIStg** method to open an IMessage interface on top of the .MSG file so that the file may be manipulated with MAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3cdc8-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cdc8-189">See also</span></span>

- [<span data-ttu-id="3cdc8-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3cdc8-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

