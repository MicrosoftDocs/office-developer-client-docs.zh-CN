---
title: IMAPIFolderCopyMessages
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: 4c7d2110-3fcb-4b9f-bf20-1dc1a611161d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21aa28e1a2c11ee7361fb4921f8d527b3e3ceb44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280125"
---
# <a name="imapifoldercopymessages"></a><span data-ttu-id="2cd2c-103">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="2cd2c-103">IMAPIFolder::CopyMessages</span></span>

  
  
<span data-ttu-id="2cd2c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2cd2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2cd2c-105">复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-105">Copies or moves one or more messages.</span></span>
  
```cpp
HRESULT CopyMessages(
  LPENTRYLIST lpMsgList,
  LPCIID lpInterface,
  LPVOID lpDestFolder,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="2cd2c-106">参数</span><span class="sxs-lookup"><span data-stu-id="2cd2c-106">Parameters</span></span>

 <span data-ttu-id="2cd2c-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="2cd2c-108">实时一个指针, 指向标识要复制或移动的邮件的[ENTRYLIST](entrylist.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that identify the message or messages to copy or move.</span></span> 
    
 <span data-ttu-id="2cd2c-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-109">_lpInterface_</span></span>
  
> <span data-ttu-id="2cd2c-110">实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问_lpDestFolder_参数指向的目标文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the destination folder pointed to by the  _lpDestFolder_ parameter.</span></span> <span data-ttu-id="2cd2c-111">在返回标准文件夹接口的服务提供程序中传递 NULL 结果, [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-111">Passing NULL results in the service provider returning the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="2cd2c-112">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-112">Clients must pass NULL.</span></span> <span data-ttu-id="2cd2c-113">其他调用方可以将_lpInterface_参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-113">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="2cd2c-114">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-114">_lpDestFolder_</span></span>
  
> <span data-ttu-id="2cd2c-115">实时指向用于接收已复制或移动的邮件的打开文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-115">[in] A pointer to the open folder to receive the copied or moved messages.</span></span>
    
 <span data-ttu-id="2cd2c-116">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-116">_ulUIParam_</span></span>
  
> <span data-ttu-id="2cd2c-117">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-117">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="2cd2c-118">_ulUIParam_参数将被忽略, 除非客户端在_ulFlags_参数中设置 MESSAGE_DIALOG 标志并在_lpProgress_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-118">The  _ulUIParam_ parameter is ignored unless the client sets the MESSAGE_DIALOG flag in the  _ulFlags_ parameter and passes NULL in the  _lpProgress_ parameter.</span></span> 
    
 <span data-ttu-id="2cd2c-119">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-119">_lpProgress_</span></span>
  
> <span data-ttu-id="2cd2c-120">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-120">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="2cd2c-121">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-121">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="2cd2c-122">除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-122">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="2cd2c-123">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2cd2c-123">_ulFlags_</span></span>
  
> <span data-ttu-id="2cd2c-124">实时用于控制如何完成复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-124">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="2cd2c-125">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2cd2c-125">The following flags can be set:</span></span>
    
<span data-ttu-id="2cd2c-126">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="2cd2c-126">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="2cd2c-127">通知邮件存储提供程序在通过调用支持对象的 IMAPISupport 来实现**IMAPIFolder:: CopyMessages**时立即返回 MAPI_E_DECLINE_COPY: [:D ocopyto](imapisupport-docopyto.md) or [IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-127">Informs the message store provider to immediately return MAPI_E_DECLINE_COPY if it implements **IMAPIFolder::CopyMessages** by calling the support object's [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) or [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method.</span></span> 
    
<span data-ttu-id="2cd2c-128">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="2cd2c-128">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="2cd2c-129">在操作继续时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-129">Displays a progress indicator as the operation proceeds.</span></span>
    
<span data-ttu-id="2cd2c-130">MESSAGE_MOVE</span><span class="sxs-lookup"><span data-stu-id="2cd2c-130">MESSAGE_MOVE</span></span> 
  
> <span data-ttu-id="2cd2c-131">要移动而不是复制的邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-131">The message or messages are to be moved instead of copied.</span></span> <span data-ttu-id="2cd2c-132">如果未设置 MESSAGE_MOVE, 则会复制邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-132">If MESSAGE_MOVE is not set, the messages are copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2cd2c-133">返回值</span><span class="sxs-lookup"><span data-stu-id="2cd2c-133">Return value</span></span>

<span data-ttu-id="2cd2c-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cd2c-134">S_OK</span></span> 
  
> <span data-ttu-id="2cd2c-135">已成功复制或移动邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-135">The message or messages have been successfully copied or moved.</span></span>
    
<span data-ttu-id="2cd2c-136">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="2cd2c-136">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="2cd2c-137">提供程序通过调用支持对象方法来实现此方法, 并且调用方已传递 MAPI_DECLINE_OK 标志。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-137">The provider implements this method by calling a support object method, and the caller has passed the MAPI_DECLINE_OK flag.</span></span>
    
<span data-ttu-id="2cd2c-138">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="2cd2c-138">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="2cd2c-139">呼叫成功, 但未成功复制或移动所有条目。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-139">The call succeeded, but not all entries were successfully copied or moved.</span></span> <span data-ttu-id="2cd2c-140">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-140">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="2cd2c-141">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-141">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="2cd2c-142">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-142">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2cd2c-143">注解</span><span class="sxs-lookup"><span data-stu-id="2cd2c-143">Remarks</span></span>

<span data-ttu-id="2cd2c-144">**IMAPIFolder:: CopyMessages**方法将邮件复制或移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-144">The **IMAPIFolder::CopyMessages** method copies or moves messages to another folder.</span></span> 
  
<span data-ttu-id="2cd2c-145">可以移动或复制以读/写权限打开的邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-145">Messages that are opened with read/write permission can be moved or copied.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2cd2c-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2cd2c-146">Notes to implementers</span></span>

<span data-ttu-id="2cd2c-147">如果不使用[IMAPISupport:: CopyMessages](imapisupport-copymessages.md)方法将邮件复制到另一个邮件存储区, 则必须先调用[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)并设置 GENERATE_RECEIPT_ONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-147">If you are copying messages to another message store without using the [IMAPISupport::CopyMessages](imapisupport-copymessages.md) method, you must first call [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) with the GENERATE_RECEIPT_ONLY flag set.</span></span> <span data-ttu-id="2cd2c-148">接收邮件存储不负责为复制或移动的邮件生成阅读报告。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-148">The receiving message store is not responsible for generating read reports for the copied or moved messages.</span></span> <span data-ttu-id="2cd2c-149">如果要调用**IMAPISupport:: CopyMessages**实现**IMAPIFolder:: CopyMessages**, 请勿调用**SetReadFlags**;MAPI 将呼叫它。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-149">If you are calling **IMAPISupport::CopyMessages** to implement **IMAPIFolder::CopyMessages**, do not call **SetReadFlags**; MAPI will call it.</span></span> 
  
<span data-ttu-id="2cd2c-150">您的实现可以按任何顺序移动或复制邮件, 并以任何顺序生成阅读状态报告。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-150">Your implementation can move or copy the messages in any order and generate read status reports in any order.</span></span> <span data-ttu-id="2cd2c-151">也就是说, 您可以在生成任何读取状态报告或在实现开始复制操作之前发送报告之前完成邮件复制。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-151">That is, you can finish copying messages before generating any of the read status reports or send the reports before your implementation starts the copy operation.</span></span> <span data-ttu-id="2cd2c-152">但是, 无论副本是否成功, 都应将阅读报告发送给所有要复制的邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-152">However, read reports should be sent for all messages to be copied, regardless of whether the copy is successful.</span></span>
  
<span data-ttu-id="2cd2c-153">当复制或移动操作涉及多封邮件时, 请尽可能完全地执行该操作。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-153">When the copy or move operation involves more than one message, perform the operation as completely as possible.</span></span> <span data-ttu-id="2cd2c-154">请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-154">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
<span data-ttu-id="2cd2c-155">请尝试在移动或复制操作中维护条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-155">Try to maintain entry identifiers across move or copy operations.</span></span> <span data-ttu-id="2cd2c-156">您还应保留条目标识符, 尽管这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-156">You should also preserve entry identifiers, although it is not required.</span></span>
  
<span data-ttu-id="2cd2c-157">移动或复制邮件时发送通知, 以便客户端 forewarned 其对邮件 " [IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法" 的调用可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-157">Send notifications when you move or copy messages so that clients are forewarned that their calls to the messages' [IMAPIProp::SaveChanges](imapiprop-savechanges.md) methods may fail.</span></span> 
  
<span data-ttu-id="2cd2c-158">请勿在复制或移动操作中包括邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-158">Do not include a message's status in the copy or move operation.</span></span> <span data-ttu-id="2cd2c-159">移动或复制邮件状态会对性能产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-159">Moving or copying a message status greatly affects performance.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="2cd2c-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2cd2c-160">Notes to callers</span></span>

<span data-ttu-id="2cd2c-161">使用**IMAPIFolder:: CopyMessages**填充搜索结果文件夹, 其中邮件通常按父文件夹进行分组。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-161">Use **IMAPIFolder::CopyMessages** to populate search-results folders, where messages are often grouped by parent folder.</span></span> 
  
<span data-ttu-id="2cd2c-162">在下列情况下, 需要这些返回值。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-162">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="2cd2c-163">**Condition**</span><span class="sxs-lookup"><span data-stu-id="2cd2c-163">**Condition**</span></span>|<span data-ttu-id="2cd2c-164">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2cd2c-164">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2cd2c-165">**IMAPIFolder:: CopyMessages**已成功复制或移动每封邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-165">**IMAPIFolder::CopyMessages** has successfully copied or moved every message.</span></span>  <br/> |<span data-ttu-id="2cd2c-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cd2c-166">S_OK</span></span>  <br/> |
|<span data-ttu-id="2cd2c-167">**IMAPIFolder:: CopyMessages**无法成功复制或移动每封邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-167">**IMAPIFolder::CopyMessages** was unable to successfully copy or move every message.</span></span>  <br/> |<span data-ttu-id="2cd2c-168">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="2cd2c-168">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="2cd2c-169">**IMAPIFolder:: CopyMessages**无法完成。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-169">**IMAPIFolder::CopyMessages** was unable to complete.</span></span>  <br/> |<span data-ttu-id="2cd2c-170">任何错误值</span><span class="sxs-lookup"><span data-stu-id="2cd2c-170">Any error value</span></span>  <br/> |
   
<span data-ttu-id="2cd2c-171">当**IMAPIFolder:: CopyMessages**无法完成时, 请不要假定没有执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-171">When **IMAPIFolder::CopyMessages** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="2cd2c-172">**IMAPIFolder:: CopyMessages**可能在遇到此错误之前能够复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="2cd2c-172">**IMAPIFolder::CopyMessages** might have been able to copy or move one or more messages before encountering the error.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2cd2c-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cd2c-173">See also</span></span>



[<span data-ttu-id="2cd2c-174">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="2cd2c-174">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

