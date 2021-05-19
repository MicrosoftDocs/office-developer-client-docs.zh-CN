---
title: IMAPIFolderGetMessageStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.GetMessageStatus
api_type:
- COM
ms.assetid: 3ddbb129-5d6b-4eca-aba0-3620609ed0c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 621c20376cc671a2ff9d1406bfb6248846e1bc81
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418636"
---
# <a name="imapifoldergetmessagestatus"></a><span data-ttu-id="7ec45-103">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="7ec45-103">IMAPIFolder::GetMessageStatus</span></span>

  
  
<span data-ttu-id="7ec45-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ec45-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ec45-105">获取与特定文件夹中的邮件相关联的状态 (例如，是否将邮件标记为删除) 。</span><span class="sxs-lookup"><span data-stu-id="7ec45-105">Obtains the status associated with a message in a particular folder (for example, whether that message is marked for deletion).</span></span>
  
```cpp
HRESULT GetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  ULONG FAR * lpulMessageStatus
);
```

## <a name="parameters"></a><span data-ttu-id="7ec45-106">参数</span><span class="sxs-lookup"><span data-stu-id="7ec45-106">Parameters</span></span>

 <span data-ttu-id="7ec45-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="7ec45-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="7ec45-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="7ec45-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="7ec45-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="7ec45-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="7ec45-110">[in]指向获取其状态的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="7ec45-110">[in] A pointer to the entry identifier for the message whose status is obtained.</span></span>
    
 <span data-ttu-id="7ec45-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7ec45-111">_ulFlags_</span></span>
  
> <span data-ttu-id="7ec45-112">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="7ec45-112">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="7ec45-113">_lpulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="7ec45-113">_lpulMessageStatus_</span></span>
  
> <span data-ttu-id="7ec45-114">[out]指向指示邮件状态的位掩码标志的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7ec45-114">[out] A pointer to a pointer to a bitmask of flags that indicate the message's status.</span></span> <span data-ttu-id="7ec45-115">保留 0 到 15 位，并且必须为零;位 16 到 31 可用于实现特定用途。</span><span class="sxs-lookup"><span data-stu-id="7ec45-115">Bits 0 through 15 are reserved and must be zero; bits 16 through 31 are available for implementation-specific use.</span></span> <span data-ttu-id="7ec45-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7ec45-116">The following flags can be set:</span></span>
    
<span data-ttu-id="7ec45-117">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="7ec45-117">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="7ec45-118">邮件已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="7ec45-118">The message has been marked for deletion.</span></span>
    
<span data-ttu-id="7ec45-119">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="7ec45-119">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="7ec45-120">不显示消息。</span><span class="sxs-lookup"><span data-stu-id="7ec45-120">The message is not to be displayed.</span></span> 
    
<span data-ttu-id="7ec45-121">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="7ec45-121">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="7ec45-122">邮件将突出显示。</span><span class="sxs-lookup"><span data-stu-id="7ec45-122">The message is to be displayed highlighted.</span></span>
    
<span data-ttu-id="7ec45-123">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="7ec45-123">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="7ec45-124">邮件已在远程邮件存储中标记为删除，无需下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="7ec45-124">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span>
    
<span data-ttu-id="7ec45-125">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="7ec45-125">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="7ec45-126">邮件已标记为从远程邮件存储下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="7ec45-126">The message has been marked for downloading from the remote message store to the local client.</span></span>
    
<span data-ttu-id="7ec45-127">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="7ec45-127">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="7ec45-128">邮件已标记为客户端定义。</span><span class="sxs-lookup"><span data-stu-id="7ec45-128">The message has been tagged for a client-defined purpose.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7ec45-129">返回值</span><span class="sxs-lookup"><span data-stu-id="7ec45-129">Return value</span></span>

<span data-ttu-id="7ec45-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ec45-130">S_OK</span></span> 
  
> <span data-ttu-id="7ec45-131">已成功检索邮件状态。</span><span class="sxs-lookup"><span data-stu-id="7ec45-131">The message status was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ec45-132">备注</span><span class="sxs-lookup"><span data-stu-id="7ec45-132">Remarks</span></span>

<span data-ttu-id="7ec45-133">**IMAPIFolder：：GetMessageStatus** 方法返回消息的状态。</span><span class="sxs-lookup"><span data-stu-id="7ec45-133">The **IMAPIFolder::GetMessageStatus** method returns the status of a message.</span></span> <span data-ttu-id="7ec45-134">邮件状态存储在邮件的邮件PR_MSG_STATUS ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="7ec45-134">Message status is stored in the message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7ec45-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="7ec45-135">Notes to implementers</span></span>

<span data-ttu-id="7ec45-136">消息状态位的设置、清除和使用方式完全取决于您的实现，除了保留 0 到 15 位，并且必须为零。</span><span class="sxs-lookup"><span data-stu-id="7ec45-136">How the message status bits are set, cleared, and used depends completely on your implementation, except that bits 0 through 15 are reserved and must be zero.</span></span> <span data-ttu-id="7ec45-137">如果将邮件存储在 IPM 子树中，MAPI 将保留 16 位到 31 位，供 IPM 客户端使用。</span><span class="sxs-lookup"><span data-stu-id="7ec45-137">If you store messages in the IPM subtree, MAPI reserves bits 16 through 31 for use by IPM clients.</span></span> <span data-ttu-id="7ec45-138">如果将邮件存储在其他子树中，可以使用位 16 到 31 来达到自己的目的。</span><span class="sxs-lookup"><span data-stu-id="7ec45-138">If you store messages in other subtrees, you can use bits 16 through 31 for your own purposes.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7ec45-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7ec45-139">MFCMAPI reference</span></span>

<span data-ttu-id="7ec45-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7ec45-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7ec45-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="7ec45-141">**File**</span></span>|<span data-ttu-id="7ec45-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="7ec45-142">**Function**</span></span>|<span data-ttu-id="7ec45-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="7ec45-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ec45-144">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="7ec45-144">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="7ec45-145">CMyMAPIFormViewer：：GetNextMessage</span><span class="sxs-lookup"><span data-stu-id="7ec45-145">CMyMAPIFormViewer::GetNextMessage</span></span>  <br/> |<span data-ttu-id="7ec45-146">MFCMAPI 使用 **IMAPIFolder：：GetMessageStatus** 方法获取要显示的下一条消息的状态。</span><span class="sxs-lookup"><span data-stu-id="7ec45-146">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the next message to be displayed.</span></span>  <br/> |
|<span data-ttu-id="7ec45-147">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="7ec45-147">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="7ec45-148">OpenMessageNonModal 和 OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="7ec45-148">OpenMessageNonModal and OpenMessageModal</span></span>  <br/> |<span data-ttu-id="7ec45-149">MFCMAPI 使用 **IMAPIFolder：：GetMessageStatus** 方法获取要显示的消息的状态以传递到表单查看器，即 CMyMAPIFormViewer 或 [IMAPISession：：ShowForm](imapisession-showform.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec45-149">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the message to be displayed to pass to the form viewer, which is either CMyMAPIFormViewer or [IMAPISession::ShowForm](imapisession-showform.md).</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7ec45-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ec45-150">See also</span></span>



[<span data-ttu-id="7ec45-151">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="7ec45-151">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
  
[<span data-ttu-id="7ec45-152">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="7ec45-152">IMAPISession::ShowForm</span></span>](imapisession-showform.md)
  
[<span data-ttu-id="7ec45-153">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ec45-153">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="7ec45-154">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="7ec45-154">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="7ec45-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7ec45-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

