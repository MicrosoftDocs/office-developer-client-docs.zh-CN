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
# <a name="imapifoldergetmessagestatus"></a><span data-ttu-id="eff61-103">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="eff61-103">IMAPIFolder::GetMessageStatus</span></span>

  
  
<span data-ttu-id="eff61-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eff61-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eff61-105">获取与特定文件夹中的邮件相关联的状态 (例如, 是否将该邮件标记为删除)。</span><span class="sxs-lookup"><span data-stu-id="eff61-105">Obtains the status associated with a message in a particular folder (for example, whether that message is marked for deletion).</span></span>
  
```cpp
HRESULT GetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  ULONG FAR * lpulMessageStatus
);
```

## <a name="parameters"></a><span data-ttu-id="eff61-106">参数</span><span class="sxs-lookup"><span data-stu-id="eff61-106">Parameters</span></span>

 <span data-ttu-id="eff61-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="eff61-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="eff61-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="eff61-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="eff61-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="eff61-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="eff61-110">实时指向已获取其状态的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="eff61-110">[in] A pointer to the entry identifier for the message whose status is obtained.</span></span>
    
 <span data-ttu-id="eff61-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="eff61-111">_ulFlags_</span></span>
  
> <span data-ttu-id="eff61-112">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="eff61-112">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="eff61-113">_lpulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="eff61-113">_lpulMessageStatus_</span></span>
  
> <span data-ttu-id="eff61-114">排除指向指示邮件状态的标志位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="eff61-114">[out] A pointer to a pointer to a bitmask of flags that indicate the message's status.</span></span> <span data-ttu-id="eff61-115">0到15位是保留的, 并且必须为零。16到31位可用于特定于实现的用途。</span><span class="sxs-lookup"><span data-stu-id="eff61-115">Bits 0 through 15 are reserved and must be zero; bits 16 through 31 are available for implementation-specific use.</span></span> <span data-ttu-id="eff61-116">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="eff61-116">The following flags can be set:</span></span>
    
<span data-ttu-id="eff61-117">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="eff61-117">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="eff61-118">邮件已被标记为删除。</span><span class="sxs-lookup"><span data-stu-id="eff61-118">The message has been marked for deletion.</span></span>
    
<span data-ttu-id="eff61-119">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="eff61-119">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="eff61-120">不显示该邮件。</span><span class="sxs-lookup"><span data-stu-id="eff61-120">The message is not to be displayed.</span></span> 
    
<span data-ttu-id="eff61-121">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="eff61-121">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="eff61-122">将突出显示该消息。</span><span class="sxs-lookup"><span data-stu-id="eff61-122">The message is to be displayed highlighted.</span></span>
    
<span data-ttu-id="eff61-123">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="eff61-123">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="eff61-124">已将邮件标记为在远程邮件存储库中删除, 而不会将其下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="eff61-124">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span>
    
<span data-ttu-id="eff61-125">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="eff61-125">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="eff61-126">已将邮件标记为从远程邮件存储下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="eff61-126">The message has been marked for downloading from the remote message store to the local client.</span></span>
    
<span data-ttu-id="eff61-127">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="eff61-127">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="eff61-128">已针对客户端定义的目的对邮件进行了标记。</span><span class="sxs-lookup"><span data-stu-id="eff61-128">The message has been tagged for a client-defined purpose.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="eff61-129">返回值</span><span class="sxs-lookup"><span data-stu-id="eff61-129">Return value</span></span>

<span data-ttu-id="eff61-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="eff61-130">S_OK</span></span> 
  
> <span data-ttu-id="eff61-131">已成功检索邮件状态。</span><span class="sxs-lookup"><span data-stu-id="eff61-131">The message status was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="eff61-132">说明</span><span class="sxs-lookup"><span data-stu-id="eff61-132">Remarks</span></span>

<span data-ttu-id="eff61-133">**IMAPIFolder:: GetMessageStatus**方法返回邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="eff61-133">The **IMAPIFolder::GetMessageStatus** method returns the status of a message.</span></span> <span data-ttu-id="eff61-134">邮件状态存储在邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="eff61-134">Message status is stored in the message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="eff61-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="eff61-135">Notes to implementers</span></span>

<span data-ttu-id="eff61-136">如何设置、清除和使用邮件状态位完全取决于您的实现, 只保留0到15位, 并且必须为零。</span><span class="sxs-lookup"><span data-stu-id="eff61-136">How the message status bits are set, cleared, and used depends completely on your implementation, except that bits 0 through 15 are reserved and must be zero.</span></span> <span data-ttu-id="eff61-137">如果将邮件存储在 IPM 子树中, MAPI 将保留位16到31以供 IPM 客户端使用。</span><span class="sxs-lookup"><span data-stu-id="eff61-137">If you store messages in the IPM subtree, MAPI reserves bits 16 through 31 for use by IPM clients.</span></span> <span data-ttu-id="eff61-138">如果将邮件存储在其他子树中, 则可以使用 bits 16 到31来实现自己的目的。</span><span class="sxs-lookup"><span data-stu-id="eff61-138">If you store messages in other subtrees, you can use bits 16 through 31 for your own purposes.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="eff61-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="eff61-139">MFCMAPI reference</span></span>

<span data-ttu-id="eff61-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="eff61-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="eff61-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="eff61-141">**File**</span></span>|<span data-ttu-id="eff61-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="eff61-142">**Function**</span></span>|<span data-ttu-id="eff61-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="eff61-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eff61-144">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="eff61-144">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="eff61-145">CMyMAPIFormViewer:: GetNextMessage</span><span class="sxs-lookup"><span data-stu-id="eff61-145">CMyMAPIFormViewer::GetNextMessage</span></span>  <br/> |<span data-ttu-id="eff61-146">MFCMAPI 使用**IMAPIFolder:: GetMessageStatus**方法获取要显示的下一封邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="eff61-146">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the next message to be displayed.</span></span>  <br/> |
|<span data-ttu-id="eff61-147">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="eff61-147">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="eff61-148">OpenMessageNonModal 和 OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="eff61-148">OpenMessageNonModal and OpenMessageModal</span></span>  <br/> |<span data-ttu-id="eff61-149">MFCMAPI 使用**IMAPIFolder:: GetMessageStatus**方法获取要显示的消息的状态, 以传递给表单查看器, 即 CMyMAPIFormViewer 或[IMAPISession:: ShowForm](imapisession-showform.md)。</span><span class="sxs-lookup"><span data-stu-id="eff61-149">MFCMAPI uses the **IMAPIFolder::GetMessageStatus** method to get the status of the message to be displayed to pass to the form viewer, which is either CMyMAPIFormViewer or [IMAPISession::ShowForm](imapisession-showform.md).</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="eff61-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eff61-150">See also</span></span>



[<span data-ttu-id="eff61-151">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="eff61-151">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
  
[<span data-ttu-id="eff61-152">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="eff61-152">IMAPISession::ShowForm</span></span>](imapisession-showform.md)
  
[<span data-ttu-id="eff61-153">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="eff61-153">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="eff61-154">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="eff61-154">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="eff61-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="eff61-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

