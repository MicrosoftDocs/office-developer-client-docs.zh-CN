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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82490dbe597ebd3f7198aa7e0c904a10202ecd77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568208"
---
# <a name="imapisupportdosentmail"></a><span data-ttu-id="a182f-103">IMAPISupport::DoSentMail</span><span class="sxs-lookup"><span data-stu-id="a182f-103">IMAPISupport::DoSentMail</span></span>

  
  
<span data-ttu-id="a182f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a182f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a182f-105">处理已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a182f-105">Processes a sent message.</span></span>
  
```cpp
HRESULT DoSentMail(
  ULONG ulFlags,
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a><span data-ttu-id="a182f-106">参数</span><span class="sxs-lookup"><span data-stu-id="a182f-106">Parameters</span></span>

 <span data-ttu-id="a182f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a182f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a182f-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="a182f-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="a182f-109">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="a182f-109">_lpMessage_</span></span>
  
> <span data-ttu-id="a182f-110">[in]一个指向打开的邮件中应为其在指定用于保存已发送的邮件文件夹中生成一条消息。</span><span class="sxs-lookup"><span data-stu-id="a182f-110">[in] A pointer to the open message for which a message should be generated in the folder designated to hold sent items.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a182f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a182f-111">Return value</span></span>

<span data-ttu-id="a182f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a182f-112">S_OK</span></span> 
  
> <span data-ttu-id="a182f-113">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="a182f-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a182f-114">注解</span><span class="sxs-lookup"><span data-stu-id="a182f-114">Remarks</span></span>

<span data-ttu-id="a182f-115">消息存储提供程序支持对象的实现**IMAPISupport::DoSentMail**方法。</span><span class="sxs-lookup"><span data-stu-id="a182f-115">The **IMAPISupport::DoSentMail** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="a182f-116">消息存储提供程序调用**DoSentMail**与[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)方法，该处理一条消息完成 MAPI 后台处理程序调用方法的实现。</span><span class="sxs-lookup"><span data-stu-id="a182f-116">Message store providers call **DoSentMail** from their implementation of the [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method, which is called by the MAPI spooler when it has finished processing a message.</span></span> <span data-ttu-id="a182f-117">**FinishedMsg**解除对邮件、 确保消息的引用计数为 1，且调用**DoSentMail**。</span><span class="sxs-lookup"><span data-stu-id="a182f-117">**FinishedMsg** unlocks the message, ensures that the message's reference count is 1, and calls **DoSentMail**.</span></span>
  
 <span data-ttu-id="a182f-118">**DoSentMail**执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a182f-118">**DoSentMail** performs the following tasks:</span></span> 
  
- <span data-ttu-id="a182f-119">检查**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性，以确定是否应发送后删除邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="a182f-119">Checks the message for the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property to determine whether the message should be deleted after sending.</span></span>
    
- <span data-ttu-id="a182f-120">确定发送邮件文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="a182f-120">Determines the location of the Sent Items folder.</span></span>
    
- <span data-ttu-id="a182f-121">启动的已发送邮件文件夹上设置任何挂接处理的消息挂钩。</span><span class="sxs-lookup"><span data-stu-id="a182f-121">Initiates message hook processing for any hooks set on the Sent Items folder.</span></span>
    
- <span data-ttu-id="a182f-122">将邮件移动到已发送邮件文件夹中，已删除邮件文件夹或另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="a182f-122">Moves the message to the Sent Items folder, Deleted Items folder, or to another folder.</span></span>
    
- <span data-ttu-id="a182f-123">发布消息。</span><span class="sxs-lookup"><span data-stu-id="a182f-123">Releases the message.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a182f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a182f-124">See also</span></span>



[<span data-ttu-id="a182f-125">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="a182f-125">IMsgStore::FinishedMsg</span></span>](imsgstore-finishedmsg.md)
  
[<span data-ttu-id="a182f-126">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="a182f-126">PidTagDeleteAfterSubmit Canonical Property</span></span>](pidtagdeleteaftersubmit-canonical-property.md)
  
[<span data-ttu-id="a182f-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a182f-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

