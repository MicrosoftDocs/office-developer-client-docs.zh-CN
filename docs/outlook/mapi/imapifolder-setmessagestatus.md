---
title: IMAPIFolderSetMessageStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SetMessageStatus
api_type:
- COM
ms.assetid: 42ffbbe0-d678-474a-a016-91c71255613e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d06523625a20760faec7a6c73a6beaef757818b3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575075"
---
# <a name="imapifoldersetmessagestatus"></a><span data-ttu-id="54eeb-103">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="54eeb-103">IMAPIFolder::SetMessageStatus</span></span>

  
  
<span data-ttu-id="54eeb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54eeb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54eeb-105">设置 （例如，无论该邮件被标记为删除） 与消息关联的状态。</span><span class="sxs-lookup"><span data-stu-id="54eeb-105">Sets the status associated with a message (for example, whether that message is marked for deletion).</span></span>
  
```cpp
HRESULT SetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulNewStatus,
  ULONG ulNewStatusMask,
  ULONG FAR * lpulOldStatus
);
```

## <a name="parameters"></a><span data-ttu-id="54eeb-106">参数</span><span class="sxs-lookup"><span data-stu-id="54eeb-106">Parameters</span></span>

 <span data-ttu-id="54eeb-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="54eeb-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="54eeb-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="54eeb-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="54eeb-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="54eeb-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="54eeb-110">[in]指向其状态设置消息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="54eeb-110">[in] A pointer to the entry identifier for the message whose status is set.</span></span>
    
 <span data-ttu-id="54eeb-111">_ulNewStatus_</span><span class="sxs-lookup"><span data-stu-id="54eeb-111">_ulNewStatus_</span></span>
  
> <span data-ttu-id="54eeb-112">[in]要分配的新状态。</span><span class="sxs-lookup"><span data-stu-id="54eeb-112">[in] The new status to be assigned.</span></span> 
    
 <span data-ttu-id="54eeb-113">_ulNewStatusMask_</span><span class="sxs-lookup"><span data-stu-id="54eeb-113">_ulNewStatusMask_</span></span>
  
> <span data-ttu-id="54eeb-114">[in]位掩码的标志应用于新的状态，并表示要设置的标志。</span><span class="sxs-lookup"><span data-stu-id="54eeb-114">[in] A bitmask of flags that is applied to the new status and indicates the flags to be set.</span></span> <span data-ttu-id="54eeb-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="54eeb-115">The following flags can be set:</span></span>
    
<span data-ttu-id="54eeb-116">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="54eeb-116">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="54eeb-117">邮件已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="54eeb-117">The message has been marked for deletion.</span></span>
    
<span data-ttu-id="54eeb-118">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="54eeb-118">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="54eeb-119">邮件是不显示。</span><span class="sxs-lookup"><span data-stu-id="54eeb-119">The message is not to be displayed.</span></span>
    
<span data-ttu-id="54eeb-120">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="54eeb-120">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="54eeb-121">邮件是显示突出显示。</span><span class="sxs-lookup"><span data-stu-id="54eeb-121">The message is to be displayed highlighted.</span></span>
    
<span data-ttu-id="54eeb-122">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="54eeb-122">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="54eeb-123">邮件已标记为删除远程邮件存储在无须下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="54eeb-123">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span>
    
<span data-ttu-id="54eeb-124">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="54eeb-124">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="54eeb-125">已从远程邮件存储下载到本地客户端标记邮件。</span><span class="sxs-lookup"><span data-stu-id="54eeb-125">The message has been marked for downloading from the remote message store to the local client.</span></span>
    
<span data-ttu-id="54eeb-126">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="54eeb-126">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="54eeb-127">邮件已标记的客户端定义用途。</span><span class="sxs-lookup"><span data-stu-id="54eeb-127">The message has been tagged for a client-defined purpose.</span></span>
    
 <span data-ttu-id="54eeb-128">_lpulOldStatus_</span><span class="sxs-lookup"><span data-stu-id="54eeb-128">_lpulOldStatus_</span></span>
  
> <span data-ttu-id="54eeb-129">[输出]一个指向邮件的以前的状态。</span><span class="sxs-lookup"><span data-stu-id="54eeb-129">[out] A pointer to the previous status of the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="54eeb-130">返回值</span><span class="sxs-lookup"><span data-stu-id="54eeb-130">Return value</span></span>

<span data-ttu-id="54eeb-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="54eeb-131">S_OK</span></span> 
  
> <span data-ttu-id="54eeb-132">已成功设置邮件状态。</span><span class="sxs-lookup"><span data-stu-id="54eeb-132">The message status was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="54eeb-133">注解</span><span class="sxs-lookup"><span data-stu-id="54eeb-133">Remarks</span></span>

<span data-ttu-id="54eeb-134">**IMAPIFolder::SetMessageStatus**方法将邮件状态设置为在其**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中存储的值。</span><span class="sxs-lookup"><span data-stu-id="54eeb-134">The **IMAPIFolder::SetMessageStatus** method sets the message status to the value that is stored in its **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="54eeb-135">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="54eeb-135">Notes to implementers</span></span>

<span data-ttu-id="54eeb-136">如何设置、 清除状态，以及使用消息状态位完全取决于您的实现，只不过 0 到 15 位保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="54eeb-136">How the message status bits are set, cleared, and used depends completely on your implementation, except that bits 0 through 15 are reserved and must be zero.</span></span> 
  
<span data-ttu-id="54eeb-137">远程传输提供程序实现此方法必须遵循此处所述的语义。</span><span class="sxs-lookup"><span data-stu-id="54eeb-137">A remote transport provider's implementation of this method must follow the semantics described here.</span></span> <span data-ttu-id="54eeb-138">没有任何特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="54eeb-138">There are no special considerations.</span></span> <span data-ttu-id="54eeb-139">客户端使用此方法可设置 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 二进制文件，以指明要下载或从远程邮件存储区删除特定的消息。</span><span class="sxs-lookup"><span data-stu-id="54eeb-139">Clients use this method to set the MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE bits to indicate that a particular message is to be downloaded or deleted from the remote message store.</span></span> <span data-ttu-id="54eeb-140">远程传输提供程序没有实现相关的[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="54eeb-140">A remote transport provider does not have to implement the related [IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) method.</span></span> <span data-ttu-id="54eeb-141">若要确定一条消息，状态的文件夹的内容表中必须查找客户端。</span><span class="sxs-lookup"><span data-stu-id="54eeb-141">Clients must look in the folder's contents table to determine the status of a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="54eeb-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="54eeb-142">Notes to callers</span></span>

<span data-ttu-id="54eeb-143">一条消息的**PR_MSG_STATUS**属性可用于协商与其他客户端的消息锁定操作。</span><span class="sxs-lookup"><span data-stu-id="54eeb-143">You can use the **PR_MSG_STATUS** property of a message to negotiate a message lockout operation with other clients.</span></span> <span data-ttu-id="54eeb-144">将指定有点为锁定位。</span><span class="sxs-lookup"><span data-stu-id="54eeb-144">Designate a bit as the lockout bit.</span></span> <span data-ttu-id="54eeb-145">若要确定是否已设置的锁定位，请检查_lpulOldStatus_参数中的邮件状态的以前值。</span><span class="sxs-lookup"><span data-stu-id="54eeb-145">To determine whether the lockout bit was set, examine the previous value for message status in the  _lpulOldStatus_ parameter.</span></span> <span data-ttu-id="54eeb-146">使用_ulNewStatus_参数中其他位而不会干扰锁定位跟踪消息状态。</span><span class="sxs-lookup"><span data-stu-id="54eeb-146">Use the other bits in the  _ulNewStatus_ parameter to track message status without interfering with the lockout bit.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="54eeb-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54eeb-147">See also</span></span>



[<span data-ttu-id="54eeb-148">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="54eeb-148">IMAPIFolder::GetMessageStatus</span></span>](imapifolder-getmessagestatus.md)
  
[<span data-ttu-id="54eeb-149">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="54eeb-149">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="54eeb-150">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="54eeb-150">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

