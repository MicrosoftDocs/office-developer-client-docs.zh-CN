---
title: IMAPISupportDoSentMail
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoSentMail
api_type:
- COM
ms.assetid: 4bb65c2a-9926-42da-9161-47836e8de40a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8289b8dd2e0ab3c760e77a37b821d2fe74e4abe9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423949"
---
# <a name="imapisupportdosentmail"></a><span data-ttu-id="1d1e0-103">IMAPISupport::DoSentMail</span><span class="sxs-lookup"><span data-stu-id="1d1e0-103">IMAPISupport::DoSentMail</span></span>

  
  
<span data-ttu-id="1d1e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d1e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d1e0-105">处理已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-105">Processes a sent message.</span></span>
  
```cpp
HRESULT DoSentMail(
  ULONG ulFlags,
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a><span data-ttu-id="1d1e0-106">参数</span><span class="sxs-lookup"><span data-stu-id="1d1e0-106">Parameters</span></span>

 <span data-ttu-id="1d1e0-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1d1e0-107">_ulFlags_</span></span>
  
> <span data-ttu-id="1d1e0-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="1d1e0-109">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="1d1e0-109">_lpMessage_</span></span>
  
> <span data-ttu-id="1d1e0-110">实时指向打开邮件的指针, 该邮件应在指定用于保存已发送邮件的文件夹中生成。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-110">[in] A pointer to the open message for which a message should be generated in the folder designated to hold sent items.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1d1e0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1d1e0-111">Return value</span></span>

<span data-ttu-id="1d1e0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d1e0-112">S_OK</span></span> 
  
> <span data-ttu-id="1d1e0-113">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1d1e0-114">说明</span><span class="sxs-lookup"><span data-stu-id="1d1e0-114">Remarks</span></span>

<span data-ttu-id="1d1e0-115">**IMAPISupport::D osentmail**方法是为邮件存储提供程序支持对象而实现的。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-115">The **IMAPISupport::DoSentMail** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="1d1e0-116">邮件存储提供程序从其[IMsgStore:: FinishedMsg](imsgstore-finishedmsg.md)方法的实现调用**DoSentMail** , 这是在处理完邮件后由 MAPI 后台处理程序调用的。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-116">Message store providers call **DoSentMail** from their implementation of the [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method, which is called by the MAPI spooler when it has finished processing a message.</span></span> <span data-ttu-id="1d1e0-117">**FinishedMsg**解除锁定邮件, 确保邮件的引用计数为 1, 并调用**DoSentMail**。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-117">**FinishedMsg** unlocks the message, ensures that the message's reference count is 1, and calls **DoSentMail**.</span></span>
  
 <span data-ttu-id="1d1e0-118">**DoSentMail**执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="1d1e0-118">**DoSentMail** performs the following tasks:</span></span> 
  
- <span data-ttu-id="1d1e0-119">检查**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性的邮件, 以确定是否应在发送后删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-119">Checks the message for the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property to determine whether the message should be deleted after sending.</span></span>
    
- <span data-ttu-id="1d1e0-120">确定 "已发送邮件" 文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-120">Determines the location of the Sent Items folder.</span></span>
    
- <span data-ttu-id="1d1e0-121">为 "已发送邮件" 文件夹上设置的任何挂接启动邮件挂钩处理。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-121">Initiates message hook processing for any hooks set on the Sent Items folder.</span></span>
    
- <span data-ttu-id="1d1e0-122">将邮件移至 "已发送邮件" 文件夹、"已删除邮件" 文件夹或其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-122">Moves the message to the Sent Items folder, Deleted Items folder, or to another folder.</span></span>
    
- <span data-ttu-id="1d1e0-123">释放邮件。</span><span class="sxs-lookup"><span data-stu-id="1d1e0-123">Releases the message.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d1e0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d1e0-124">See also</span></span>



[<span data-ttu-id="1d1e0-125">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="1d1e0-125">IMsgStore::FinishedMsg</span></span>](imsgstore-finishedmsg.md)
  
[<span data-ttu-id="1d1e0-126">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d1e0-126">PidTagDeleteAfterSubmit Canonical Property</span></span>](pidtagdeleteaftersubmit-canonical-property.md)
  
[<span data-ttu-id="1d1e0-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1d1e0-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

