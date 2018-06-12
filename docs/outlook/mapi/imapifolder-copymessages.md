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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e6e9e9cefc75ffc78ee7beb47e89063ea1a66ce7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775345"
---
# <a name="imapifoldercopymessages"></a><span data-ttu-id="cf7e4-103">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="cf7e4-103">IMAPIFolder::CopyMessages</span></span>

  
  
<span data-ttu-id="cf7e4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cf7e4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cf7e4-105">复制或移动一个或多条消息。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-105">Copies or moves one or more messages.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="cf7e4-106">参数</span><span class="sxs-lookup"><span data-stu-id="cf7e4-106">Parameters</span></span>

 <span data-ttu-id="cf7e4-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="cf7e4-108">[in]指向一个标识要复制或移动的消息的[ENTRYLIST](entrylist.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that identify the message or messages to copy or move.</span></span> 
    
 <span data-ttu-id="cf7e4-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-109">_lpInterface_</span></span>
  
> <span data-ttu-id="cf7e4-110">[in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestFolder_参数指向目标文件夹的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the destination folder pointed to by the  _lpDestFolder_ parameter.</span></span> <span data-ttu-id="cf7e4-111">传递 NULL 将导致服务提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-111">Passing NULL results in the service provider returning the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="cf7e4-112">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-112">Clients must pass NULL.</span></span> <span data-ttu-id="cf7e4-113">其他呼叫者可以设置为 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 或 IID_IMAPIFolder _lpInterface_参数。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-113">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="cf7e4-114">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-114">_lpDestFolder_</span></span>
  
> <span data-ttu-id="cf7e4-115">[in]指向打开接收复制或移动邮件文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-115">[in] A pointer to the open folder to receive the copied or moved messages.</span></span>
    
 <span data-ttu-id="cf7e4-116">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-116">_ulUIParam_</span></span>
  
> <span data-ttu-id="cf7e4-117">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-117">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="cf7e4-118">除非在客户端中_ulFlags_参数设置 MESSAGE_DIALOG 标志和_lpProgress_参数中传递 NULL，则将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-118">The  _ulUIParam_ parameter is ignored unless the client sets the MESSAGE_DIALOG flag in the  _ulFlags_ parameter and passes NULL in the  _lpProgress_ parameter.</span></span> 
    
 <span data-ttu-id="cf7e4-119">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-119">_lpProgress_</span></span>
  
> <span data-ttu-id="cf7e4-120">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-120">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="cf7e4-121">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-121">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="cf7e4-122">除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-122">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="cf7e4-123">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cf7e4-123">_ulFlags_</span></span>
  
> <span data-ttu-id="cf7e4-124">[in]位掩码的标志，控制如何完成复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-124">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="cf7e4-125">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cf7e4-125">The following flags can be set:</span></span>
    
<span data-ttu-id="cf7e4-126">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="cf7e4-126">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="cf7e4-127">通知如果它通过调用支持对象的[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)或[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法实现**IMAPIFolder::CopyMessages**立即返回 MAPI_E_DECLINE_COPY 消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-127">Informs the message store provider to immediately return MAPI_E_DECLINE_COPY if it implements **IMAPIFolder::CopyMessages** by calling the support object's [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) or [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method.</span></span> 
    
<span data-ttu-id="cf7e4-128">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="cf7e4-128">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="cf7e4-129">随着进行操作，则显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-129">Displays a progress indicator as the operation proceeds.</span></span>
    
<span data-ttu-id="cf7e4-130">MESSAGE_MOVE</span><span class="sxs-lookup"><span data-stu-id="cf7e4-130">MESSAGE_MOVE</span></span> 
  
> <span data-ttu-id="cf7e4-131">邮件或消息是移动而不是复制。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-131">The message or messages are to be moved instead of copied.</span></span> <span data-ttu-id="cf7e4-132">如果未设置 MESSAGE_MOVE，邮件所复制。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-132">If MESSAGE_MOVE is not set, the messages are copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cf7e4-133">返回值</span><span class="sxs-lookup"><span data-stu-id="cf7e4-133">Return value</span></span>

<span data-ttu-id="cf7e4-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf7e4-134">S_OK</span></span> 
  
> <span data-ttu-id="cf7e4-135">邮件已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-135">The message or messages have been successfully copied or moved.</span></span>
    
<span data-ttu-id="cf7e4-136">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="cf7e4-136">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="cf7e4-137">提供程序实现此方法通过调用支持对象方法，并且将呼叫者已传递 MAPI_DECLINE_OK 标志。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-137">The provider implements this method by calling a support object method, and the caller has passed the MAPI_DECLINE_OK flag.</span></span>
    
<span data-ttu-id="cf7e4-138">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="cf7e4-138">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="cf7e4-139">调用成功，但并非所有项已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-139">The call succeeded, but not all entries were successfully copied or moved.</span></span> <span data-ttu-id="cf7e4-140">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-140">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="cf7e4-141">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-141">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="cf7e4-142">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-142">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cf7e4-143">备注</span><span class="sxs-lookup"><span data-stu-id="cf7e4-143">Remarks</span></span>

<span data-ttu-id="cf7e4-144">**IMAPIFolder::CopyMessages**方法复制，或将邮件移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-144">The **IMAPIFolder::CopyMessages** method copies or moves messages to another folder.</span></span> 
  
<span data-ttu-id="cf7e4-145">使用打开的邮件读/写权限可以移动或复制。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-145">Messages that are opened with read/write permission can be moved or copied.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="cf7e4-146">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="cf7e4-146">Notes to implementers</span></span>

<span data-ttu-id="cf7e4-147">如果您到另一个消息存储库复制邮件，而无需使用[IMAPISupport::CopyMessages](imapisupport-copymessages.md)方法，您必须先调用[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)设置了 GENERATE_RECEIPT_ONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-147">If you are copying messages to another message store without using the [IMAPISupport::CopyMessages](imapisupport-copymessages.md) method, you must first call [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) with the GENERATE_RECEIPT_ONLY flag set.</span></span> <span data-ttu-id="cf7e4-148">接收方的消息存储不负责生成的复制或移动邮件阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-148">The receiving message store is not responsible for generating read reports for the copied or moved messages.</span></span> <span data-ttu-id="cf7e4-149">如果您正在呼叫**IMAPISupport::CopyMessages**实现**IMAPIFolder::CopyMessages**，不会调用**SetReadFlags**;MAPI 将调用它。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-149">If you are calling **IMAPISupport::CopyMessages** to implement **IMAPIFolder::CopyMessages**, do not call **SetReadFlags**; MAPI will call it.</span></span> 
  
<span data-ttu-id="cf7e4-150">实现可以移动或复制的邮件，按任意顺序并按任意顺序生成读取的状态报告。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-150">Your implementation can move or copy the messages in any order and generate read status reports in any order.</span></span> <span data-ttu-id="cf7e4-151">即可以完成之前生成读取的状态任何的报告复制邮件或实现开始复制操作之前发送报告。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-151">That is, you can finish copying messages before generating any of the read status reports or send the reports before your implementation starts the copy operation.</span></span> <span data-ttu-id="cf7e4-152">但是，读取报告应发送的所有邮件不管副本是否成功复制。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-152">However, read reports should be sent for all messages to be copied, regardless of whether the copy is successful.</span></span>
  
<span data-ttu-id="cf7e4-153">当复制或移动操作涉及多个邮件时，请尽可能完整执行操作。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-153">When the copy or move operation involves more than one message, perform the operation as completely as possible.</span></span> <span data-ttu-id="cf7e4-154">不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-154">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
<span data-ttu-id="cf7e4-155">尝试移动或复制操作在维护条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-155">Try to maintain entry identifiers across move or copy operations.</span></span> <span data-ttu-id="cf7e4-156">尽管不需要，还应保留项标识符。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-156">You should also preserve entry identifiers, although it is not required.</span></span>
  
<span data-ttu-id="cf7e4-157">移动或复制邮件，以便客户端注意其调用邮件的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法可能会失败时发送通知。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-157">Send notifications when you move or copy messages so that clients are forewarned that their calls to the messages' [IMAPIProp::SaveChanges](imapiprop-savechanges.md) methods may fail.</span></span> 
  
<span data-ttu-id="cf7e4-158">不要在副本中包括邮件的状态或移动操作。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-158">Do not include a message's status in the copy or move operation.</span></span> <span data-ttu-id="cf7e4-159">移动或复制邮件状态会显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-159">Moving or copying a message status greatly affects performance.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="cf7e4-160">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="cf7e4-160">Notes to callers</span></span>

<span data-ttu-id="cf7e4-161">使用**IMAPIFolder::CopyMessages**填充搜索结果文件夹，其中邮件通常组合的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-161">Use **IMAPIFolder::CopyMessages** to populate search-results folders, where messages are often grouped by parent folder.</span></span> 
  
<span data-ttu-id="cf7e4-162">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-162">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="cf7e4-163">**条件**</span><span class="sxs-lookup"><span data-stu-id="cf7e4-163">**Condition**</span></span>|<span data-ttu-id="cf7e4-164">**返回值**</span><span class="sxs-lookup"><span data-stu-id="cf7e4-164">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf7e4-165">**IMAPIFolder::CopyMessages**已成功复制或移动的每条消息。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-165">**IMAPIFolder::CopyMessages** has successfully copied or moved every message.</span></span>  <br/> |<span data-ttu-id="cf7e4-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf7e4-166">S_OK</span></span>  <br/> |
|<span data-ttu-id="cf7e4-167">**IMAPIFolder::CopyMessages**程序无法成功复制或移动的每条消息。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-167">**IMAPIFolder::CopyMessages** was unable to successfully copy or move every message.</span></span>  <br/> |<span data-ttu-id="cf7e4-168">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="cf7e4-168">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="cf7e4-169">**IMAPIFolder::CopyMessages**无法完成。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-169">**IMAPIFolder::CopyMessages** was unable to complete.</span></span>  <br/> |<span data-ttu-id="cf7e4-170">任何错误值</span><span class="sxs-lookup"><span data-stu-id="cf7e4-170">Any error value</span></span>  <br/> |
   
<span data-ttu-id="cf7e4-171">无法完成**IMAPIFolder::CopyMessages**时，不假定任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-171">When **IMAPIFolder::CopyMessages** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="cf7e4-172">**IMAPIFolder::CopyMessages**可能已经能够邮件复制或移动一个或多个之前遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cf7e4-172">**IMAPIFolder::CopyMessages** might have been able to copy or move one or more messages before encountering the error.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cf7e4-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf7e4-173">See also</span></span>



[<span data-ttu-id="cf7e4-174">IMAPIFolder: IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="cf7e4-174">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

