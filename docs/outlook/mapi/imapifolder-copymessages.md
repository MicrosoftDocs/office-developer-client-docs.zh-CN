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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424453"
---
# <a name="imapifoldercopymessages"></a><span data-ttu-id="a0e2a-103">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="a0e2a-103">IMAPIFolder::CopyMessages</span></span>

  
  
<span data-ttu-id="a0e2a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0e2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0e2a-105">复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-105">Copies or moves one or more messages.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a0e2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0e2a-106">Parameters</span></span>

 <span data-ttu-id="a0e2a-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="a0e2a-108">[in]指向标识要复制或移动的邮件 [的 ENTRYLIST](entrylist.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that identify the message or messages to copy or move.</span></span> 
    
 <span data-ttu-id="a0e2a-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-109">_lpInterface_</span></span>
  
> <span data-ttu-id="a0e2a-110">[in]指向接口标识符的指针 (IID) 表示用于访问  _lpDestFolder_ 参数指向的目标文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the destination folder pointed to by the  _lpDestFolder_ parameter.</span></span> <span data-ttu-id="a0e2a-111">传递 NULL 会导致服务提供商返回标准文件夹接口 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-111">Passing NULL results in the service provider returning the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="a0e2a-112">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-112">Clients must pass NULL.</span></span> <span data-ttu-id="a0e2a-113">其他调用方可以将  _lpInterface_ 参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-113">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="a0e2a-114">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-114">_lpDestFolder_</span></span>
  
> <span data-ttu-id="a0e2a-115">[in]一个指向打开文件夹的指针，用于接收复制或移动的邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-115">[in] A pointer to the open folder to receive the copied or moved messages.</span></span>
    
 <span data-ttu-id="a0e2a-116">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-116">_ulUIParam_</span></span>
  
> <span data-ttu-id="a0e2a-117">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-117">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="a0e2a-118">除非客户端在 _ulFlags_ 参数中设置 MESSAGE_DIALOG 标志，并传递 _lpProgress_ 参数中的 NULL，否则将忽略 _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-118">The  _ulUIParam_ parameter is ignored unless the client sets the MESSAGE_DIALOG flag in the  _ulFlags_ parameter and passes NULL in the  _lpProgress_ parameter.</span></span> 
    
 <span data-ttu-id="a0e2a-119">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-119">_lpProgress_</span></span>
  
> <span data-ttu-id="a0e2a-120">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-120">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="a0e2a-121">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-121">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="a0e2a-122">除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-122">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="a0e2a-123">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a0e2a-123">_ulFlags_</span></span>
  
> <span data-ttu-id="a0e2a-124">[in]控制复制或移动操作完成方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-124">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="a0e2a-125">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a0e2a-125">The following flags can be set:</span></span>
    
<span data-ttu-id="a0e2a-126">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="a0e2a-126">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="a0e2a-127">如果邮件存储提供程序通过调用支持对象的 [IMAPISupport：:D oCopyTo](imapisupport-docopyto.md)或 [IMAPISupport：:D oCopyProps](imapisupport-docopyprops.md)方法实现 **IMAPIFolder：：CopyMessages，** 则通知其立即返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-127">Informs the message store provider to immediately return MAPI_E_DECLINE_COPY if it implements **IMAPIFolder::CopyMessages** by calling the support object's [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) or [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method.</span></span> 
    
<span data-ttu-id="a0e2a-128">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a0e2a-128">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="a0e2a-129">在操作继续时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-129">Displays a progress indicator as the operation proceeds.</span></span>
    
<span data-ttu-id="a0e2a-130">MESSAGE_MOVE</span><span class="sxs-lookup"><span data-stu-id="a0e2a-130">MESSAGE_MOVE</span></span> 
  
> <span data-ttu-id="a0e2a-131">要移动而不是复制邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-131">The message or messages are to be moved instead of copied.</span></span> <span data-ttu-id="a0e2a-132">如果未MESSAGE_MOVE，则复制邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-132">If MESSAGE_MOVE is not set, the messages are copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a0e2a-133">返回值</span><span class="sxs-lookup"><span data-stu-id="a0e2a-133">Return value</span></span>

<span data-ttu-id="a0e2a-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0e2a-134">S_OK</span></span> 
  
> <span data-ttu-id="a0e2a-135">已成功复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-135">The message or messages have been successfully copied or moved.</span></span>
    
<span data-ttu-id="a0e2a-136">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="a0e2a-136">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="a0e2a-137">提供程序通过调用支持对象方法来实现此方法，并且调用方已传递MAPI_DECLINE_OK标志。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-137">The provider implements this method by calling a support object method, and the caller has passed the MAPI_DECLINE_OK flag.</span></span>
    
<span data-ttu-id="a0e2a-138">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="a0e2a-138">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="a0e2a-139">调用成功，但并非所有条目都已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-139">The call succeeded, but not all entries were successfully copied or moved.</span></span> <span data-ttu-id="a0e2a-140">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-140">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="a0e2a-141">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-141">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="a0e2a-142">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-142">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a0e2a-143">备注</span><span class="sxs-lookup"><span data-stu-id="a0e2a-143">Remarks</span></span>

<span data-ttu-id="a0e2a-144">**IMAPIFolder：：CopyMessages** 方法将邮件复制或移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-144">The **IMAPIFolder::CopyMessages** method copies or moves messages to another folder.</span></span> 
  
<span data-ttu-id="a0e2a-145">使用读/写权限打开的邮件可以移动或复制。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-145">Messages that are opened with read/write permission can be moved or copied.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a0e2a-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a0e2a-146">Notes to implementers</span></span>

<span data-ttu-id="a0e2a-147">如果要在未使用[IMAPISupport：：CopyMessages](imapisupport-copymessages.md)方法的情况下将邮件复制到其他邮件存储，则必须先调用设置了 GENERATE_RECEIPT_ONLY 标志的[IMAPIFolder：：SetReadFlags。](imapifolder-setreadflags.md)</span><span class="sxs-lookup"><span data-stu-id="a0e2a-147">If you are copying messages to another message store without using the [IMAPISupport::CopyMessages](imapisupport-copymessages.md) method, you must first call [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) with the GENERATE_RECEIPT_ONLY flag set.</span></span> <span data-ttu-id="a0e2a-148">接收邮件存储不负责为复制或移动的邮件生成读取报告。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-148">The receiving message store is not responsible for generating read reports for the copied or moved messages.</span></span> <span data-ttu-id="a0e2a-149">如果要调用 **IMAPISupport：：CopyMessages** 来实现 **IMAPIFolder：：CopyMessages，** 请不要调用 **SetReadFlags**;MAPI 将调用它。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-149">If you are calling **IMAPISupport::CopyMessages** to implement **IMAPIFolder::CopyMessages**, do not call **SetReadFlags**; MAPI will call it.</span></span> 
  
<span data-ttu-id="a0e2a-150">你的实现可以按任何顺序移动或复制邮件，并按任何顺序生成读取状态报告。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-150">Your implementation can move or copy the messages in any order and generate read status reports in any order.</span></span> <span data-ttu-id="a0e2a-151">也就是说，您可以在生成任何已读状态报告之前完成邮件复制，或在实现开始复制操作之前发送报告。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-151">That is, you can finish copying messages before generating any of the read status reports or send the reports before your implementation starts the copy operation.</span></span> <span data-ttu-id="a0e2a-152">但是，应为要复制的所有邮件发送阅读报告，而不管复制是否成功。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-152">However, read reports should be sent for all messages to be copied, regardless of whether the copy is successful.</span></span>
  
<span data-ttu-id="a0e2a-153">当复制或移动操作涉及多条消息时，请尽可能完全执行该操作。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-153">When the copy or move operation involves more than one message, perform the operation as completely as possible.</span></span> <span data-ttu-id="a0e2a-154">除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-154">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
<span data-ttu-id="a0e2a-155">尝试跨移动或复制操作维护条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-155">Try to maintain entry identifiers across move or copy operations.</span></span> <span data-ttu-id="a0e2a-156">您还应该保留条目标识符，尽管这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-156">You should also preserve entry identifiers, although it is not required.</span></span>
  
<span data-ttu-id="a0e2a-157">在移动或复制邮件时发送通知，以便客户端预想其对消息 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法的调用可能会失败。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-157">Send notifications when you move or copy messages so that clients are forewarned that their calls to the messages' [IMAPIProp::SaveChanges](imapiprop-savechanges.md) methods may fail.</span></span> 
  
<span data-ttu-id="a0e2a-158">请勿在复制或移动操作中包括邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-158">Do not include a message's status in the copy or move operation.</span></span> <span data-ttu-id="a0e2a-159">移动或复制邮件状态会大大影响性能。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-159">Moving or copying a message status greatly affects performance.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="a0e2a-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a0e2a-160">Notes to callers</span></span>

<span data-ttu-id="a0e2a-161">使用 **IMAPIFolder：：CopyMessages** 填充搜索结果文件夹，其中邮件通常按父文件夹进行分组。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-161">Use **IMAPIFolder::CopyMessages** to populate search-results folders, where messages are often grouped by parent folder.</span></span> 
  
<span data-ttu-id="a0e2a-162">预计以下情况下会返回这些值。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-162">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="a0e2a-163">**Condition**</span><span class="sxs-lookup"><span data-stu-id="a0e2a-163">**Condition**</span></span>|<span data-ttu-id="a0e2a-164">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a0e2a-164">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0e2a-165">**IMAPIFolder：：CopyMessages** 已成功复制或移动每封邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-165">**IMAPIFolder::CopyMessages** has successfully copied or moved every message.</span></span>  <br/> |<span data-ttu-id="a0e2a-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0e2a-166">S_OK</span></span>  <br/> |
|<span data-ttu-id="a0e2a-167">**IMAPIFolder：：CopyMessages** 无法成功复制或移动每条消息。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-167">**IMAPIFolder::CopyMessages** was unable to successfully copy or move every message.</span></span>  <br/> |<span data-ttu-id="a0e2a-168">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="a0e2a-168">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="a0e2a-169">**IMAPIFolder：：CopyMessages** 无法完成。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-169">**IMAPIFolder::CopyMessages** was unable to complete.</span></span>  <br/> |<span data-ttu-id="a0e2a-170">任何错误值</span><span class="sxs-lookup"><span data-stu-id="a0e2a-170">Any error value</span></span>  <br/> |
   
<span data-ttu-id="a0e2a-171">当 **IMAPIFolder：：CopyMessages** 无法完成时，不要假定未完成任何工作。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-171">When **IMAPIFolder::CopyMessages** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="a0e2a-172">**IMAPIFolder：：CopyMessages** 可能能够在遇到错误之前复制或移动一个或多个消息。</span><span class="sxs-lookup"><span data-stu-id="a0e2a-172">**IMAPIFolder::CopyMessages** might have been able to copy or move one or more messages before encountering the error.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a0e2a-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e2a-173">See also</span></span>



[<span data-ttu-id="a0e2a-174">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="a0e2a-174">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

