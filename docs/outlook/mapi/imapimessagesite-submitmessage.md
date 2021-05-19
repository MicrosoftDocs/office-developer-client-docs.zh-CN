---
title: IMAPIMessageSiteSubmitMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.SubmitMessage
api_type:
- COM
ms.assetid: 6b14c383-8bc6-4e86-bd92-0500272af40d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 496732e334d2d39672048dd1a02346aaee4b70e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417026"
---
# <a name="imapimessagesitesubmitmessage"></a><span data-ttu-id="da86d-103">IMAPIMessageSite::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="da86d-103">IMAPIMessageSite::SubmitMessage</span></span>

  
  
<span data-ttu-id="da86d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da86d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da86d-105">请求将当前邮件排入队列进行传递。</span><span class="sxs-lookup"><span data-stu-id="da86d-105">Requests that the current message be queued for delivery.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="da86d-106">参数</span><span class="sxs-lookup"><span data-stu-id="da86d-106">Parameters</span></span>

 <span data-ttu-id="da86d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="da86d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="da86d-108">[in]控制邮件提交方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="da86d-108">[in] A bitmask of flags that controls how a message is submitted.</span></span> <span data-ttu-id="da86d-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="da86d-109">The following flag can be set:</span></span>
    
<span data-ttu-id="da86d-110">FORCE_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="da86d-110">FORCE_SUBMIT</span></span> 
  
> <span data-ttu-id="da86d-111">MAPI 应该提交邮件，即使可能不会立即发送。</span><span class="sxs-lookup"><span data-stu-id="da86d-111">MAPI should submit the message even if it might not be sent immediately.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="da86d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="da86d-112">Return value</span></span>

<span data-ttu-id="da86d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="da86d-113">S_OK</span></span> 
  
> <span data-ttu-id="da86d-114">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="da86d-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="da86d-115">备注</span><span class="sxs-lookup"><span data-stu-id="da86d-115">Remarks</span></span>

<span data-ttu-id="da86d-116">Form 对象调用 **IMAPIMessageSite：：SubmitMessage** 方法，以请求将邮件排队等待传递。</span><span class="sxs-lookup"><span data-stu-id="da86d-116">Form objects call the **IMAPIMessageSite::SubmitMessage** method to request that a message be queued for delivery.</span></span> <span data-ttu-id="da86d-117">邮件网站应在提交邮件之前调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="da86d-117">The message site should call the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method before submitting the message.</span></span> <span data-ttu-id="da86d-118">邮件不需要以前保存，因为 **SubmitMessage** 应在邮件已修改时导致邮件保存。</span><span class="sxs-lookup"><span data-stu-id="da86d-118">The message does not need to have been previously saved, because **SubmitMessage** should cause the message to be saved if the message has been modified.</span></span> <span data-ttu-id="da86d-119">返回 **SubmitMessage** 后，表单必须检查当前邮件，然后在不存在邮件时自行消除。</span><span class="sxs-lookup"><span data-stu-id="da86d-119">After the return of **SubmitMessage**, the form must check for a current message and then dismiss itself if none exists.</span></span> 
  
<span data-ttu-id="da86d-120">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="da86d-120">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="da86d-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="da86d-121">MFCMAPI reference</span></span>

<span data-ttu-id="da86d-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="da86d-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="da86d-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="da86d-123">**File**</span></span>|<span data-ttu-id="da86d-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="da86d-124">**Function**</span></span>|<span data-ttu-id="da86d-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="da86d-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da86d-126">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="da86d-126">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="da86d-127">CMyMAPIFormViewer：：SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="da86d-127">CMyMAPIFormViewer::SubmitMessage</span></span>  <br/> |<span data-ttu-id="da86d-128">MFCMAPI 使用 **IMAPIMessageSite：：SubmitMessage** 方法保存邮件。</span><span class="sxs-lookup"><span data-stu-id="da86d-128">MFCMAPI uses the **IMAPIMessageSite::SubmitMessage** method to save the message.</span></span> <span data-ttu-id="da86d-129">首先，它调用 **IPersistMessage：：HandsOffMessage** 方法，然后调用 **SubmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="da86d-129">First, it calls the **IPersistMessage::HandsOffMessage** method, and then it calls **SubmitMessage**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="da86d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da86d-130">See also</span></span>



[<span data-ttu-id="da86d-131">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="da86d-131">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="da86d-132">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="da86d-132">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="da86d-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="da86d-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="da86d-134">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="da86d-134">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

