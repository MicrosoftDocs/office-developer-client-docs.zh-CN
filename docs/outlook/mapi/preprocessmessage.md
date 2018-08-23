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
ms.openlocfilehash: 878c3aaf22a6cf8a08c8234df41b671088c435c7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584987"
---
# <a name="preprocessmessage"></a><span data-ttu-id="86753-103">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="86753-103">PreprocessMessage</span></span>

  
  
<span data-ttu-id="86753-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86753-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86753-105">定义预处理邮件内容或一条消息的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="86753-105">Defines a function that preprocesses message contents or the format of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86753-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="86753-106">Header file:</span></span>  <br/> |<span data-ttu-id="86753-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="86753-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="86753-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="86753-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="86753-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="86753-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="86753-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="86753-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="86753-111">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="86753-111">MAPI spooler</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="86753-112">参数</span><span class="sxs-lookup"><span data-stu-id="86753-112">Parameters</span></span>

 <span data-ttu-id="86753-113">_lpvSession_</span><span class="sxs-lookup"><span data-stu-id="86753-113">_lpvSession_</span></span>
  
> <span data-ttu-id="86753-114">[in]加入会话，从而使用指针。</span><span class="sxs-lookup"><span data-stu-id="86753-114">[in] Pointer to the session to be used.</span></span> 
    
 <span data-ttu-id="86753-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="86753-115">_lpMessage_</span></span>
  
> <span data-ttu-id="86753-116">[in]指向预处理的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="86753-116">[in] Pointer to the message to be preprocessed.</span></span> 
    
 <span data-ttu-id="86753-117">_lpAdrBook_</span><span class="sxs-lookup"><span data-stu-id="86753-117">_lpAdrBook_</span></span>
  
> <span data-ttu-id="86753-118">[in]对通讯簿用户应从中选择的邮件收件人的指针。</span><span class="sxs-lookup"><span data-stu-id="86753-118">[in] Pointer to the address book from which the user should select recipients for the message.</span></span> 
    
 <span data-ttu-id="86753-119">_lpFolder_</span><span class="sxs-lookup"><span data-stu-id="86753-119">_lpFolder_</span></span>
  
> <span data-ttu-id="86753-120">[传入、 传出]指向文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="86753-120">[in, out] Pointer to a folder.</span></span> <span data-ttu-id="86753-121">在输入_lpFolder_参数指向包含邮件预处理的文件夹。</span><span class="sxs-lookup"><span data-stu-id="86753-121">On input, the  _lpFolder_ parameter points to the folder that contains messages to be preprocessed.</span></span> <span data-ttu-id="86753-122">输出， _lpFolder_指向预处理的消息放置位置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="86753-122">On output,  _lpFolder_ points to the folder where preprocessed messages have been placed.</span></span> 
    
 <span data-ttu-id="86753-123">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="86753-123">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="86753-124">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="86753-124">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="86753-125">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="86753-125">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="86753-126">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存在需要时。</span><span class="sxs-lookup"><span data-stu-id="86753-126">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory where required.</span></span> 
    
 <span data-ttu-id="86753-127">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="86753-127">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="86753-128">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="86753-128">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="86753-129">_lpcOutbound_</span><span class="sxs-lookup"><span data-stu-id="86753-129">_lpcOutbound_</span></span>
  
> <span data-ttu-id="86753-130">[输出]指向_lpppMessage_参数指向该数组中的消息数。</span><span class="sxs-lookup"><span data-stu-id="86753-130">[out] Pointer to the number of messages in the array pointed to by the  _lpppMessage_ parameter.</span></span> 
    
 <span data-ttu-id="86753-131">_lpppMessage_</span><span class="sxs-lookup"><span data-stu-id="86753-131">_lpppMessage_</span></span>
  
> <span data-ttu-id="86753-132">[输出]为数组指向指针的指针预处理或否则生成的邮件。</span><span class="sxs-lookup"><span data-stu-id="86753-132">[out] Pointer to a pointer to an array of pointers to preprocessed or otherwise generated messages.</span></span> 
    
 <span data-ttu-id="86753-133">_lppRecipList_</span><span class="sxs-lookup"><span data-stu-id="86753-133">_lppRecipList_</span></span>
  
> <span data-ttu-id="86753-134">[输出]为可选的指针返回[ADRLIST](adrlist.md)结构，列出其邮件是未送达的预处理器检测到的收件人。</span><span class="sxs-lookup"><span data-stu-id="86753-134">[out] Pointer to an optional returned [ADRLIST](adrlist.md) structure, listing preprocessor-detected recipients for which the message is undeliverable.</span></span> <span data-ttu-id="86753-135">此列表的内容的详细信息，请参阅[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法。</span><span class="sxs-lookup"><span data-stu-id="86753-135">For more information about the contents of this list, see the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="86753-136">返回值</span><span class="sxs-lookup"><span data-stu-id="86753-136">Return value</span></span>

<span data-ttu-id="86753-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="86753-137">S_OK</span></span>
  
> <span data-ttu-id="86753-138">邮件内容已成功预处理。</span><span class="sxs-lookup"><span data-stu-id="86753-138">Message contents were successfully preprocessed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="86753-139">注解</span><span class="sxs-lookup"><span data-stu-id="86753-139">Remarks</span></span>

<span data-ttu-id="86753-140">传输提供程序消息预处理器消息预处理期间可以演示的进度指示器。</span><span class="sxs-lookup"><span data-stu-id="86753-140">A transport-provider message preprocessor can present a progress indicator during message preprocessing.</span></span> <span data-ttu-id="86753-141">但是，它应永远不会显示一个对话框，需要用户交互期间消息预处理。</span><span class="sxs-lookup"><span data-stu-id="86753-141">However, it should never present a dialog box requiring user interaction during message preprocessing.</span></span> 
  
<span data-ttu-id="86753-142">预处理器将大量数据添加到出站邮件时, 应遵循某些过程。</span><span class="sxs-lookup"><span data-stu-id="86753-142">When a preprocessor adds large amounts of data to an outbound message, certain procedures should be followed.</span></span> <span data-ttu-id="86753-143">此类型的消息可以存储在基于服务器的邮件存储区，导致预处理器访问远程存储区，非常耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="86753-143">This type of message can be stored in a server-based message store, causing the preprocessor to access a remote store, a time-consuming procedure.</span></span> <span data-ttu-id="86753-144">若要避免这样做，预处理器应具有该选项，使其以存储大量空间采用本地邮件存储区中的数据并提供对本地邮件中存储的引用。</span><span class="sxs-lookup"><span data-stu-id="86753-144">To avoid having to do so, the preprocessor should have an option that enables it to store data that takes a large amount of space in a local message store and to provide a reference to that local store in the message.</span></span> 
  
<span data-ttu-id="86753-145">预处理器不应释放的任何最初传递给**PreprocessMessage**基于函数对象。</span><span class="sxs-lookup"><span data-stu-id="86753-145">The preprocessor should not release any of the objects originally passed to the **PreprocessMessage** based function.</span></span> 
  
<span data-ttu-id="86753-146">MAPI 后台处理程序可以调用**PreprocessMessage**函数之前，必须具有传输提供程序注册[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法将调用的函数。</span><span class="sxs-lookup"><span data-stu-id="86753-146">Before the MAPI spooler can call a **PreprocessMessage** function, the transport provider must have registered the function in a call to the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method.</span></span> <span data-ttu-id="86753-147">在调用**PreprocessMessage**函数，后台处理程序无法继续提交一条消息，直到此函数返回。</span><span class="sxs-lookup"><span data-stu-id="86753-147">After calling a **PreprocessMessage** function, the spooler cannot continue submitting a message until the function returns.</span></span> 
  
<span data-ttu-id="86753-148">MAPI 后台处理程序负责提交邮件的任务。</span><span class="sxs-lookup"><span data-stu-id="86753-148">The MAPI spooler owns the task of submitting messages.</span></span> <span data-ttu-id="86753-149">这意味着原始邮件永远不放置数组中的邮件指针而且**SubmitMessage**方法调用从来不是必需。</span><span class="sxs-lookup"><span data-stu-id="86753-149">This means the original message is never placed in an array of message pointers and that a call to the **SubmitMessage** methods is never required.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="86753-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86753-150">See also</span></span>



[<span data-ttu-id="86753-151">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="86753-151">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="86753-152">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="86753-152">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="86753-153">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="86753-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

