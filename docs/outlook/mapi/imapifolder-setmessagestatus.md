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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fbb05efff67fa90c68db86249d4657e489e7bd63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342775"
---
# <a name="imapifoldersetmessagestatus"></a><span data-ttu-id="14c44-103">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="14c44-103">IMAPIFolder::SetMessageStatus</span></span>

  
  
<span data-ttu-id="14c44-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="14c44-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="14c44-105">设置与邮件关联的状态 (例如, 是否将该邮件标记为要删除)。</span><span class="sxs-lookup"><span data-stu-id="14c44-105">Sets the status associated with a message (for example, whether that message is marked for deletion).</span></span>
  
```cpp
HRESULT SetMessageStatus(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulNewStatus,
  ULONG ulNewStatusMask,
  ULONG FAR * lpulOldStatus
);
```

## <a name="parameters"></a><span data-ttu-id="14c44-106">参数</span><span class="sxs-lookup"><span data-stu-id="14c44-106">Parameters</span></span>

 <span data-ttu-id="14c44-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="14c44-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="14c44-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="14c44-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="14c44-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="14c44-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="14c44-110">实时指向其状态为设置的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="14c44-110">[in] A pointer to the entry identifier for the message whose status is set.</span></span>
    
 <span data-ttu-id="14c44-111">_ulNewStatus_</span><span class="sxs-lookup"><span data-stu-id="14c44-111">_ulNewStatus_</span></span>
  
> <span data-ttu-id="14c44-112">实时要分配的新状态。</span><span class="sxs-lookup"><span data-stu-id="14c44-112">[in] The new status to be assigned.</span></span> 
    
 <span data-ttu-id="14c44-113">_ulNewStatusMask_</span><span class="sxs-lookup"><span data-stu-id="14c44-113">_ulNewStatusMask_</span></span>
  
> <span data-ttu-id="14c44-114">实时应用于新状态并指示要设置的标志的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="14c44-114">[in] A bitmask of flags that is applied to the new status and indicates the flags to be set.</span></span> <span data-ttu-id="14c44-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="14c44-115">The following flags can be set:</span></span>
    
<span data-ttu-id="14c44-116">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="14c44-116">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="14c44-117">邮件已被标记为删除。</span><span class="sxs-lookup"><span data-stu-id="14c44-117">The message has been marked for deletion.</span></span>
    
<span data-ttu-id="14c44-118">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="14c44-118">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="14c44-119">不显示该邮件。</span><span class="sxs-lookup"><span data-stu-id="14c44-119">The message is not to be displayed.</span></span>
    
<span data-ttu-id="14c44-120">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="14c44-120">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="14c44-121">将突出显示该消息。</span><span class="sxs-lookup"><span data-stu-id="14c44-121">The message is to be displayed highlighted.</span></span>
    
<span data-ttu-id="14c44-122">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="14c44-122">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="14c44-123">已将邮件标记为在远程邮件存储库中删除, 而不会将其下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="14c44-123">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span>
    
<span data-ttu-id="14c44-124">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="14c44-124">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="14c44-125">已将邮件标记为从远程邮件存储下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="14c44-125">The message has been marked for downloading from the remote message store to the local client.</span></span>
    
<span data-ttu-id="14c44-126">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="14c44-126">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="14c44-127">已针对客户端定义的目的对邮件进行了标记。</span><span class="sxs-lookup"><span data-stu-id="14c44-127">The message has been tagged for a client-defined purpose.</span></span>
    
 <span data-ttu-id="14c44-128">_lpulOldStatus_</span><span class="sxs-lookup"><span data-stu-id="14c44-128">_lpulOldStatus_</span></span>
  
> <span data-ttu-id="14c44-129">排除指向邮件的上一个状态的指针。</span><span class="sxs-lookup"><span data-stu-id="14c44-129">[out] A pointer to the previous status of the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="14c44-130">返回值</span><span class="sxs-lookup"><span data-stu-id="14c44-130">Return value</span></span>

<span data-ttu-id="14c44-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="14c44-131">S_OK</span></span> 
  
> <span data-ttu-id="14c44-132">已成功设置邮件状态。</span><span class="sxs-lookup"><span data-stu-id="14c44-132">The message status was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="14c44-133">注解</span><span class="sxs-lookup"><span data-stu-id="14c44-133">Remarks</span></span>

<span data-ttu-id="14c44-134">**IMAPIFolder:: SetMessageStatus**方法将邮件状态设置为存储在其**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的值。</span><span class="sxs-lookup"><span data-stu-id="14c44-134">The **IMAPIFolder::SetMessageStatus** method sets the message status to the value that is stored in its **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="14c44-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="14c44-135">Notes to implementers</span></span>

<span data-ttu-id="14c44-136">如何设置、清除和使用邮件状态位完全取决于您的实现, 只保留0到15位, 并且必须为零。</span><span class="sxs-lookup"><span data-stu-id="14c44-136">How the message status bits are set, cleared, and used depends completely on your implementation, except that bits 0 through 15 are reserved and must be zero.</span></span> 
  
<span data-ttu-id="14c44-137">此方法的远程传输提供程序的实现必须遵循此处所述的语义。</span><span class="sxs-lookup"><span data-stu-id="14c44-137">A remote transport provider's implementation of this method must follow the semantics described here.</span></span> <span data-ttu-id="14c44-138">没有特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="14c44-138">There are no special considerations.</span></span> <span data-ttu-id="14c44-139">客户端使用此方法来设置 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 位, 以指示要从远程邮件存储中下载或删除特定邮件。</span><span class="sxs-lookup"><span data-stu-id="14c44-139">Clients use this method to set the MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE bits to indicate that a particular message is to be downloaded or deleted from the remote message store.</span></span> <span data-ttu-id="14c44-140">远程传输提供程序无需实现相关的[IMAPIFolder:: GetMessageStatus](imapifolder-getmessagestatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="14c44-140">A remote transport provider does not have to implement the related [IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) method.</span></span> <span data-ttu-id="14c44-141">客户端必须在文件夹的内容表中查找, 以确定邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="14c44-141">Clients must look in the folder's contents table to determine the status of a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="14c44-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="14c44-142">Notes to callers</span></span>

<span data-ttu-id="14c44-143">可以使用邮件的**PR_MSG_STATUS**属性将邮件锁定操作与其他客户端进行协商。</span><span class="sxs-lookup"><span data-stu-id="14c44-143">You can use the **PR_MSG_STATUS** property of a message to negotiate a message lockout operation with other clients.</span></span> <span data-ttu-id="14c44-144">将一个位指定为锁定位。</span><span class="sxs-lookup"><span data-stu-id="14c44-144">Designate a bit as the lockout bit.</span></span> <span data-ttu-id="14c44-145">若要确定是否设置了锁定位, 请在_lpulOldStatus_参数中检查邮件状态的以前的值。</span><span class="sxs-lookup"><span data-stu-id="14c44-145">To determine whether the lockout bit was set, examine the previous value for message status in the  _lpulOldStatus_ parameter.</span></span> <span data-ttu-id="14c44-146">使用_ulNewStatus_参数中的其他位跟踪邮件状态, 而不影响锁定位。</span><span class="sxs-lookup"><span data-stu-id="14c44-146">Use the other bits in the  _ulNewStatus_ parameter to track message status without interfering with the lockout bit.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="14c44-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14c44-147">See also</span></span>



[<span data-ttu-id="14c44-148">IMAPIFolder::GetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="14c44-148">IMAPIFolder::GetMessageStatus</span></span>](imapifolder-getmessagestatus.md)
  
[<span data-ttu-id="14c44-149">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="14c44-149">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="14c44-150">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="14c44-150">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

