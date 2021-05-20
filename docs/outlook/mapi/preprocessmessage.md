---
title: PreprocessMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PreprocessMessage
api_type:
- COM
ms.assetid: dda50325-74b3-445e-986e-115f6536561f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a3982520cb1c745874a938962ece075a294b6257
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437243"
---
# <a name="preprocessmessage"></a><span data-ttu-id="6c59a-103">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="6c59a-103">PreprocessMessage</span></span>

  
  
<span data-ttu-id="6c59a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c59a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c59a-105">定义一个预处理邮件内容或邮件格式的函数。</span><span class="sxs-lookup"><span data-stu-id="6c59a-105">Defines a function that preprocesses message contents or the format of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6c59a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6c59a-106">Header file:</span></span>  <br/> |<span data-ttu-id="6c59a-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="6c59a-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="6c59a-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="6c59a-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="6c59a-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="6c59a-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="6c59a-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="6c59a-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="6c59a-111">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="6c59a-111">MAPI spooler</span></span>  <br/> |
   
```cpp
HRESULT PreprocessMessage(
  LPVOID lpvSession,
  LPMESSAGE lpMessage,
  LPADRBOOK lpAdrBook,
  LPMAPIFOLDER lpFolder,
  LPALLOCATEBUFFER AllocateBuffer,
  LPALLOCATEMORE AllocateMore,
  LPFREEBUFFER FreeBuffer,
  ULONG FAR * lpcOutbound,
  LPMESSAGE FAR * FAR * lpppMessage,
  LPADRLIST FAR * lppRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="6c59a-112">参数</span><span class="sxs-lookup"><span data-stu-id="6c59a-112">Parameters</span></span>

 <span data-ttu-id="6c59a-113">_lpvSession_</span><span class="sxs-lookup"><span data-stu-id="6c59a-113">_lpvSession_</span></span>
  
> <span data-ttu-id="6c59a-114">[in]指向要使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="6c59a-114">[in] Pointer to the session to be used.</span></span> 
    
 <span data-ttu-id="6c59a-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="6c59a-115">_lpMessage_</span></span>
  
> <span data-ttu-id="6c59a-116">[in]指向要预处理的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="6c59a-116">[in] Pointer to the message to be preprocessed.</span></span> 
    
 <span data-ttu-id="6c59a-117">_lpAdrBook_</span><span class="sxs-lookup"><span data-stu-id="6c59a-117">_lpAdrBook_</span></span>
  
> <span data-ttu-id="6c59a-118">[in]指向用户应从中选择邮件收件人的通讯簿的指针。</span><span class="sxs-lookup"><span data-stu-id="6c59a-118">[in] Pointer to the address book from which the user should select recipients for the message.</span></span> 
    
 <span data-ttu-id="6c59a-119">_lpFolder_</span><span class="sxs-lookup"><span data-stu-id="6c59a-119">_lpFolder_</span></span>
  
> <span data-ttu-id="6c59a-120">[in， out]指向文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="6c59a-120">[in, out] Pointer to a folder.</span></span> <span data-ttu-id="6c59a-121">在输入时  _，lpFolder_ 参数指向包含要预处理的邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c59a-121">On input, the  _lpFolder_ parameter points to the folder that contains messages to be preprocessed.</span></span> <span data-ttu-id="6c59a-122">在输出时  _，lpFolder_ 指向放置预处理邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c59a-122">On output,  _lpFolder_ points to the folder where preprocessed messages have been placed.</span></span> 
    
 <span data-ttu-id="6c59a-123">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="6c59a-123">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="6c59a-124">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="6c59a-124">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="6c59a-125">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="6c59a-125">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="6c59a-126">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配所需的额外内存。</span><span class="sxs-lookup"><span data-stu-id="6c59a-126">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory where required.</span></span> 
    
 <span data-ttu-id="6c59a-127">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="6c59a-127">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="6c59a-128">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="6c59a-128">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="6c59a-129">_lpcOutbound_</span><span class="sxs-lookup"><span data-stu-id="6c59a-129">_lpcOutbound_</span></span>
  
> <span data-ttu-id="6c59a-130">[out]指向  _lpppMessage_ 参数指向的数组中的邮件数的指针。</span><span class="sxs-lookup"><span data-stu-id="6c59a-130">[out] Pointer to the number of messages in the array pointed to by the  _lpppMessage_ parameter.</span></span> 
    
 <span data-ttu-id="6c59a-131">_lpppMessage_</span><span class="sxs-lookup"><span data-stu-id="6c59a-131">_lpppMessage_</span></span>
  
> <span data-ttu-id="6c59a-132">[out]指向指向指针数组的指针的指针，指向预处理或以其他方式生成的消息。</span><span class="sxs-lookup"><span data-stu-id="6c59a-132">[out] Pointer to a pointer to an array of pointers to preprocessed or otherwise generated messages.</span></span> 
    
 <span data-ttu-id="6c59a-133">_lppRecipList_</span><span class="sxs-lookup"><span data-stu-id="6c59a-133">_lppRecipList_</span></span>
  
> <span data-ttu-id="6c59a-134">[out]指向可选返回的 [ADRLIST](adrlist.md) 结构的指针，列出邮件无法送达的预处理器检测到的收件人。</span><span class="sxs-lookup"><span data-stu-id="6c59a-134">[out] Pointer to an optional returned [ADRLIST](adrlist.md) structure, listing preprocessor-detected recipients for which the message is undeliverable.</span></span> <span data-ttu-id="6c59a-135">有关此列表的内容详细信息，请参阅 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6c59a-135">For more information about the contents of this list, see the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6c59a-136">返回值</span><span class="sxs-lookup"><span data-stu-id="6c59a-136">Return value</span></span>

<span data-ttu-id="6c59a-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c59a-137">S_OK</span></span>
  
> <span data-ttu-id="6c59a-138">邮件内容已成功预处理。</span><span class="sxs-lookup"><span data-stu-id="6c59a-138">Message contents were successfully preprocessed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6c59a-139">备注</span><span class="sxs-lookup"><span data-stu-id="6c59a-139">Remarks</span></span>

<span data-ttu-id="6c59a-140">传输提供程序邮件预处理器可以在邮件预处理期间显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="6c59a-140">A transport-provider message preprocessor can present a progress indicator during message preprocessing.</span></span> <span data-ttu-id="6c59a-141">但是，它永远不应在消息预处理期间显示需要用户交互的对话框。</span><span class="sxs-lookup"><span data-stu-id="6c59a-141">However, it should never present a dialog box requiring user interaction during message preprocessing.</span></span> 
  
<span data-ttu-id="6c59a-142">当预处理器向出站邮件添加大量数据时，应执行某些过程。</span><span class="sxs-lookup"><span data-stu-id="6c59a-142">When a preprocessor adds large amounts of data to an outbound message, certain procedures should be followed.</span></span> <span data-ttu-id="6c59a-143">此类消息可以存储在基于服务器的邮件存储中，从而导致预处理器访问远程存储，这是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="6c59a-143">This type of message can be stored in a server-based message store, causing the preprocessor to access a remote store, a time-consuming procedure.</span></span> <span data-ttu-id="6c59a-144">为了避免必须这样做，预处理器应具有一个选项，使预处理器能够将占用大量空间的数据存储在本地邮件存储中，并提供对邮件中该本地存储的引用。</span><span class="sxs-lookup"><span data-stu-id="6c59a-144">To avoid having to do so, the preprocessor should have an option that enables it to store data that takes a large amount of space in a local message store and to provide a reference to that local store in the message.</span></span> 
  
<span data-ttu-id="6c59a-145">预处理器不应释放最初传递给基于 **PreprocessMessage** 的函数的任何对象。</span><span class="sxs-lookup"><span data-stu-id="6c59a-145">The preprocessor should not release any of the objects originally passed to the **PreprocessMessage** based function.</span></span> 
  
<span data-ttu-id="6c59a-146">在 MAPI 后台处理程序可以调用 **PreprocessMessage** 函数之前，传输提供程序必须在 [对 IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md) 方法的调用中注册该函数。</span><span class="sxs-lookup"><span data-stu-id="6c59a-146">Before the MAPI spooler can call a **PreprocessMessage** function, the transport provider must have registered the function in a call to the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method.</span></span> <span data-ttu-id="6c59a-147">调用 **PreprocessMessage** 函数后，后台处理程序无法继续提交邮件，直到函数返回。</span><span class="sxs-lookup"><span data-stu-id="6c59a-147">After calling a **PreprocessMessage** function, the spooler cannot continue submitting a message until the function returns.</span></span> 
  
<span data-ttu-id="6c59a-148">MAPI 后台处理程序拥有提交邮件的任务。</span><span class="sxs-lookup"><span data-stu-id="6c59a-148">The MAPI spooler owns the task of submitting messages.</span></span> <span data-ttu-id="6c59a-149">这意味着原始邮件永远不会放置在消息指针数组中，并且从不需要调用 **SubmitMessage** 方法。</span><span class="sxs-lookup"><span data-stu-id="6c59a-149">This means the original message is never placed in an array of message pointers and that a call to the **SubmitMessage** methods is never required.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6c59a-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c59a-150">See also</span></span>



[<span data-ttu-id="6c59a-151">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6c59a-151">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="6c59a-152">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="6c59a-152">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="6c59a-153">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6c59a-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

