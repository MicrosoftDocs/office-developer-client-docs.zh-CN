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
ms.openlocfilehash: 8e5ccadbd6df664b6650487f340508ae4548a1c2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583265"
---
# <a name="imapifoldergetmessagestatus"></a><span data-ttu-id="f4894-103">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="f4894-103">IMAPIFolder::GetMessageStatus</span></span>

  
  
<span data-ttu-id="f4894-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4894-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4894-105">获取与特定的文件夹中的邮件 （例如，无论该邮件被标记为删除） 的状态。</span><span class="sxs-lookup"><span data-stu-id="f4894-105">Obtains the status associated with a message in a particular folder (for example, whether that message is marked for deletion).</span></span>
  
```cpp
HRESULT GetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  ULONG FAR * lpulMessageStatus
);
```

## <a name="parameters"></a><span data-ttu-id="f4894-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4894-106">Parameters</span></span>

 <span data-ttu-id="f4894-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="f4894-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="f4894-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="f4894-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="f4894-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="f4894-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="f4894-110">[in]指向获得其状态的消息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="f4894-110">[in] A pointer to the entry identifier for the message whose status is obtained.</span></span>
    
 <span data-ttu-id="f4894-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f4894-111">_ulFlags_</span></span>
  
> <span data-ttu-id="f4894-112">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f4894-112">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="f4894-113">_lpulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="f4894-113">_lpulMessageStatus_</span></span>
  
> <span data-ttu-id="f4894-114">[输出]指向指示邮件的状态标志的位掩码的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f4894-114">[out] A pointer to a pointer to a bitmask of flags that indicate the message's status.</span></span> <span data-ttu-id="f4894-115">0 到 15 位保留，必须为零;位到 31 16 是可用于特定于实现的。</span><span class="sxs-lookup"><span data-stu-id="f4894-115">Bits 0 through 15 are reserved and must be zero; bits 16 through 31 are available for implementation-specific use.</span></span> <span data-ttu-id="f4894-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f4894-116">The following flags can be set:</span></span>
    
<span data-ttu-id="f4894-117">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="f4894-117">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="f4894-118">邮件已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="f4894-118">The message has been marked for deletion.</span></span>
    
<span data-ttu-id="f4894-119">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="f4894-119">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="f4894-120">邮件是不显示。</span><span class="sxs-lookup"><span data-stu-id="f4894-120">The message is not to be displayed.</span></span> 
    
<span data-ttu-id="f4894-121">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="f4894-121">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="f4894-122">邮件是显示突出显示。</span><span class="sxs-lookup"><span data-stu-id="f4894-122">The message is to be displayed highlighted.</span></span>
    
<span data-ttu-id="f4894-123">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="f4894-123">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="f4894-124">邮件已标记为删除远程邮件存储在无须下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="f4894-124">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span>
    
<span data-ttu-id="f4894-125">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="f4894-125">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="f4894-126">已从远程邮件存储下载到本地客户端标记邮件。</span><span class="sxs-lookup"><span data-stu-id="f4894-126">The message has been marked for downloading from the remote message store to the local client.</span></span>
    
<span data-ttu-id="f4894-127">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="f4894-127">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="f4894-128">邮件已标记的客户端定义用途。</span><span class="sxs-lookup"><span data-stu-id="f4894-128">The message has been tagged for a client-defined purpose.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f4894-129">返回值</span><span class="sxs-lookup"><span data-stu-id="f4894-129">Return value</span></span>

<span data-ttu-id="f4894-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4894-130">S_OK</span></span> 
  
> <span data-ttu-id="f4894-131">已成功检索邮件状态。</span><span class="sxs-lookup"><span data-stu-id="f4894-131">The message status was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f4894-132">注解</span><span class="sxs-lookup"><span data-stu-id="f4894-132">Remarks</span></span>

<span data-ttu-id="f4894-133">**IMAPIFolder::GetMessageStatus**方法返回一条消息，的状态。</span><span class="sxs-lookup"><span data-stu-id="f4894-133">The **IMAPIFolder::GetMessageStatus** method returns the status of a message.</span></span> <span data-ttu-id="f4894-134">邮件状态存储在消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="f4894-134">Message status is stored in the message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f4894-135">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="f4894-135">Notes to implementers</span></span>

<span data-ttu-id="f4894-136">如何设置、 清除状态，以及使用消息状态位完全取决于您的实现，只不过 0 到 15 位保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="f4894-136">How the message status bits are set, cleared, and used depends completely on your implementation, except that bits 0 through 15 are reserved and must be zero.</span></span> <span data-ttu-id="f4894-137">如果将消息存储 IPM 子树中，MAPI 保留 IPM 客户端通过使用 31 16 位。</span><span class="sxs-lookup"><span data-stu-id="f4894-137">If you store messages in the IPM subtree, MAPI reserves bits 16 through 31 for use by IPM clients.</span></span> <span data-ttu-id="f4894-138">如果将消息存储在其他子树中，您可用于通过 31 16 位自己的目的。</span><span class="sxs-lookup"><span data-stu-id="f4894-138">If you store messages in other subtrees, you can use bits 16 through 31 for your own purposes.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f4894-139">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="f4894-139">MFCMAPI reference</span></span>

<span data-ttu-id="f4894-140">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f4894-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f4894-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="f4894-141">**File**</span></span>|<span data-ttu-id="f4894-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="f4894-142">**Function**</span></span>|<span data-ttu-id="f4894-143">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f4894-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4894-144">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="f4894-144">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="f4894-145">CMyMAPIFormViewer::GetNextMessage</span><span class="sxs-lookup"><span data-stu-id="f4894-145">CMyMAPIFormViewer::GetNextMessage</span></span>  <br/> |<span data-ttu-id="f4894-146">MFCMAPI 使用**IMAPIFolder::GetMessageStatus**方法来获取的状态将显示下一条消息。</span><span class="sxs-lookup"><span data-stu-id="f4894-146">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the next message to be displayed.</span></span>  <br/> |
|<span data-ttu-id="f4894-147">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="f4894-147">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="f4894-148">OpenMessageNonModal 和 OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="f4894-148">OpenMessageNonModal and OpenMessageModal</span></span>  <br/> |<span data-ttu-id="f4894-149">MFCMAPI 使用**IMAPIFolder::GetMessageStatus**方法来获取要传递给表单查看器中，即 CMyMAPIFormViewer 或[IMAPISession::ShowForm](imapisession-showform.md)要显示的消息的状态。</span><span class="sxs-lookup"><span data-stu-id="f4894-149">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the message to be displayed to pass to the form viewer, which is either CMyMAPIFormViewer or [IMAPISession::ShowForm](imapisession-showform.md).</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f4894-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4894-150">See also</span></span>



[<span data-ttu-id="f4894-151">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="f4894-151">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
  
[<span data-ttu-id="f4894-152">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="f4894-152">IMAPISession::ShowForm</span></span>](imapisession-showform.md)
  
[<span data-ttu-id="f4894-153">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="f4894-153">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="f4894-154">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="f4894-154">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="f4894-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f4894-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

