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
# <a name="preprocessmessage"></a><span data-ttu-id="e11e4-103">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="e11e4-103">PreprocessMessage</span></span>

  
  
<span data-ttu-id="e11e4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e11e4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e11e4-105">定义预处理邮件内容或邮件格式的函数。</span><span class="sxs-lookup"><span data-stu-id="e11e4-105">Defines a function that preprocesses message contents or the format of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e11e4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e11e4-106">Header file:</span></span>  <br/> |<span data-ttu-id="e11e4-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="e11e4-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="e11e4-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="e11e4-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="e11e4-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="e11e4-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="e11e4-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="e11e4-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="e11e4-111">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="e11e4-111">MAPI spooler</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="e11e4-112">参数</span><span class="sxs-lookup"><span data-stu-id="e11e4-112">Parameters</span></span>

 <span data-ttu-id="e11e4-113">_lpvSession_</span><span class="sxs-lookup"><span data-stu-id="e11e4-113">_lpvSession_</span></span>
  
> <span data-ttu-id="e11e4-114">实时指向要使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-114">[in] Pointer to the session to be used.</span></span> 
    
 <span data-ttu-id="e11e4-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="e11e4-115">_lpMessage_</span></span>
  
> <span data-ttu-id="e11e4-116">实时指向要进行预处理的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-116">[in] Pointer to the message to be preprocessed.</span></span> 
    
 <span data-ttu-id="e11e4-117">_lpAdrBook_</span><span class="sxs-lookup"><span data-stu-id="e11e4-117">_lpAdrBook_</span></span>
  
> <span data-ttu-id="e11e4-118">实时指向用户应从中选择邮件收件人的通讯簿的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-118">[in] Pointer to the address book from which the user should select recipients for the message.</span></span> 
    
 <span data-ttu-id="e11e4-119">_lpFolder_</span><span class="sxs-lookup"><span data-stu-id="e11e4-119">_lpFolder_</span></span>
  
> <span data-ttu-id="e11e4-120">[in, out]指向文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-120">[in, out] Pointer to a folder.</span></span> <span data-ttu-id="e11e4-121">在输入时, _lpFolder_参数指向包含要进行预处理的邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e11e4-121">On input, the  _lpFolder_ parameter points to the folder that contains messages to be preprocessed.</span></span> <span data-ttu-id="e11e4-122">在输出时, _lpFolder_指向已放置预处理邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e11e4-122">On output,  _lpFolder_ points to the folder where preprocessed messages have been placed.</span></span> 
    
 <span data-ttu-id="e11e4-123">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="e11e4-123">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="e11e4-124">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-124">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="e11e4-125">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="e11e4-125">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="e11e4-126">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 用于在需要时分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="e11e4-126">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory where required.</span></span> 
    
 <span data-ttu-id="e11e4-127">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="e11e4-127">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="e11e4-128">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-128">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="e11e4-129">_lpcOutbound_</span><span class="sxs-lookup"><span data-stu-id="e11e4-129">_lpcOutbound_</span></span>
  
> <span data-ttu-id="e11e4-130">排除一个指针, 指向由_lpppMessage_参数指向的数组中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="e11e4-130">[out] Pointer to the number of messages in the array pointed to by the  _lpppMessage_ parameter.</span></span> 
    
 <span data-ttu-id="e11e4-131">_lpppMessage_</span><span class="sxs-lookup"><span data-stu-id="e11e4-131">_lpppMessage_</span></span>
  
> <span data-ttu-id="e11e4-132">排除指向指向经过预处理或以其他方式生成的邮件的指针数组的指针。</span><span class="sxs-lookup"><span data-stu-id="e11e4-132">[out] Pointer to a pointer to an array of pointers to preprocessed or otherwise generated messages.</span></span> 
    
 <span data-ttu-id="e11e4-133">_lppRecipList_</span><span class="sxs-lookup"><span data-stu-id="e11e4-133">_lppRecipList_</span></span>
  
> <span data-ttu-id="e11e4-134">排除指向可选的返回[ADRLIST](adrlist.md)结构的指针, 其中列出了预处理器检测到的无法传递邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="e11e4-134">[out] Pointer to an optional returned [ADRLIST](adrlist.md) structure, listing preprocessor-detected recipients for which the message is undeliverable.</span></span> <span data-ttu-id="e11e4-135">有关此列表内容的详细信息, 请参阅[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e11e4-135">For more information about the contents of this list, see the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e11e4-136">返回值</span><span class="sxs-lookup"><span data-stu-id="e11e4-136">Return value</span></span>

<span data-ttu-id="e11e4-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="e11e4-137">S_OK</span></span>
  
> <span data-ttu-id="e11e4-138">邮件内容已成功预处理。</span><span class="sxs-lookup"><span data-stu-id="e11e4-138">Message contents were successfully preprocessed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e11e4-139">说明</span><span class="sxs-lookup"><span data-stu-id="e11e4-139">Remarks</span></span>

<span data-ttu-id="e11e4-140">传输提供程序消息预处理器可在邮件预处理过程中显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e11e4-140">A transport-provider message preprocessor can present a progress indicator during message preprocessing.</span></span> <span data-ttu-id="e11e4-141">但是, 它决不应显示在邮件预处理过程中需要用户交互的对话框。</span><span class="sxs-lookup"><span data-stu-id="e11e4-141">However, it should never present a dialog box requiring user interaction during message preprocessing.</span></span> 
  
<span data-ttu-id="e11e4-142">当预处理器向出站邮件中添加大量数据时, 应遵循某些过程。</span><span class="sxs-lookup"><span data-stu-id="e11e4-142">When a preprocessor adds large amounts of data to an outbound message, certain procedures should be followed.</span></span> <span data-ttu-id="e11e4-143">这种类型的邮件可以存储在基于服务器的邮件存储中, 从而导致预处理器访问远程存储, 这是一种耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="e11e4-143">This type of message can be stored in a server-based message store, causing the preprocessor to access a remote store, a time-consuming procedure.</span></span> <span data-ttu-id="e11e4-144">若要避免这种情况, 预处理器应具有一个选项, 使其能够存储在本地邮件存储区中占用大量空间的数据, 并在邮件中提供对该本地存储区的引用。</span><span class="sxs-lookup"><span data-stu-id="e11e4-144">To avoid having to do so, the preprocessor should have an option that enables it to store data that takes a large amount of space in a local message store and to provide a reference to that local store in the message.</span></span> 
  
<span data-ttu-id="e11e4-145">预处理器不应释放最初传递到基于**PreprocessMessage**的函数的任何对象。</span><span class="sxs-lookup"><span data-stu-id="e11e4-145">The preprocessor should not release any of the objects originally passed to the **PreprocessMessage** based function.</span></span> 
  
<span data-ttu-id="e11e4-146">在 MAPI 后台处理程序可以调用**PreprocessMessage**函数之前, 传输提供程序必须已在对[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法的调用中注册了函数。</span><span class="sxs-lookup"><span data-stu-id="e11e4-146">Before the MAPI spooler can call a **PreprocessMessage** function, the transport provider must have registered the function in a call to the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method.</span></span> <span data-ttu-id="e11e4-147">调用**PreprocessMessage**函数后, 后台打印程序将无法继续提交邮件, 直到函数返回为止。</span><span class="sxs-lookup"><span data-stu-id="e11e4-147">After calling a **PreprocessMessage** function, the spooler cannot continue submitting a message until the function returns.</span></span> 
  
<span data-ttu-id="e11e4-148">MAPI 后台处理程序拥有提交邮件的任务。</span><span class="sxs-lookup"><span data-stu-id="e11e4-148">The MAPI spooler owns the task of submitting messages.</span></span> <span data-ttu-id="e11e4-149">这意味着原始邮件从不放置在邮件指针的数组中, 并且从不需要对**SubmitMessage**方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e11e4-149">This means the original message is never placed in an array of message pointers and that a call to the **SubmitMessage** methods is never required.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e11e4-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e11e4-150">See also</span></span>



[<span data-ttu-id="e11e4-151">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e11e4-151">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="e11e4-152">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e11e4-152">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="e11e4-153">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e11e4-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

