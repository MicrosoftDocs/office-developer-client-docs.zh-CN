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
# <a name="imapimessagesitesubmitmessage"></a><span data-ttu-id="bf1c1-103">IMAPIMessageSite::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="bf1c1-103">IMAPIMessageSite::SubmitMessage</span></span>

  
  
<span data-ttu-id="bf1c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf1c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf1c1-105">请求将当前邮件排队等待传递。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-105">Requests that the current message be queued for delivery.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="bf1c1-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf1c1-106">Parameters</span></span>

 <span data-ttu-id="bf1c1-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bf1c1-107">_ulFlags_</span></span>
  
> <span data-ttu-id="bf1c1-108">实时控制如何提交邮件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-108">[in] A bitmask of flags that controls how a message is submitted.</span></span> <span data-ttu-id="bf1c1-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="bf1c1-109">The following flag can be set:</span></span>
    
<span data-ttu-id="bf1c1-110">FORCE_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="bf1c1-110">FORCE_SUBMIT</span></span> 
  
> <span data-ttu-id="bf1c1-111">MAPI 应提交邮件, 即使它可能不会立即发送。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-111">MAPI should submit the message even if it might not be sent immediately.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bf1c1-112">返回值</span><span class="sxs-lookup"><span data-stu-id="bf1c1-112">Return value</span></span>

<span data-ttu-id="bf1c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf1c1-113">S_OK</span></span> 
  
> <span data-ttu-id="bf1c1-114">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bf1c1-115">说明</span><span class="sxs-lookup"><span data-stu-id="bf1c1-115">Remarks</span></span>

<span data-ttu-id="bf1c1-116">表单对象调用**IMAPIMessageSite:: SubmitMessage**方法以请求将邮件排队等待传递。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-116">Form objects call the **IMAPIMessageSite::SubmitMessage** method to request that a message be queued for delivery.</span></span> <span data-ttu-id="bf1c1-117">邮件网站在提交邮件之前, 应调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-117">The message site should call the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method before submitting the message.</span></span> <span data-ttu-id="bf1c1-118">该邮件不需要先保存, 因为如果邮件已被修改, **SubmitMessage**应会导致保存邮件。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-118">The message does not need to have been previously saved, because **SubmitMessage** should cause the message to be saved if the message has been modified.</span></span> <span data-ttu-id="bf1c1-119">返回**SubmitMessage**后, 该窗体必须检查当前邮件, 然后在不存在的情况下消除自己。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-119">After the return of **SubmitMessage**, the form must check for a current message and then dismiss itself if none exists.</span></span> 
  
<span data-ttu-id="bf1c1-120">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-120">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bf1c1-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="bf1c1-121">MFCMAPI reference</span></span>

<span data-ttu-id="bf1c1-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bf1c1-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="bf1c1-123">**File**</span></span>|<span data-ttu-id="bf1c1-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="bf1c1-124">**Function**</span></span>|<span data-ttu-id="bf1c1-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="bf1c1-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf1c1-126">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="bf1c1-126">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="bf1c1-127">CMyMAPIFormViewer:: SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="bf1c1-127">CMyMAPIFormViewer::SubmitMessage</span></span>  <br/> |<span data-ttu-id="bf1c1-128">MFCMAPI 使用**IMAPIMessageSite:: SubmitMessage**方法保存邮件。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-128">MFCMAPI uses the **IMAPIMessageSite::SubmitMessage** method to save the message.</span></span> <span data-ttu-id="bf1c1-129">首先, 它调用**IPersistMessage:: HandsOffMessage**方法, 然后调用**SubmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="bf1c1-129">First, it calls the **IPersistMessage::HandsOffMessage** method, and then it calls **SubmitMessage**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bf1c1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf1c1-130">See also</span></span>



[<span data-ttu-id="bf1c1-131">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="bf1c1-131">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="bf1c1-132">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bf1c1-132">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="bf1c1-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bf1c1-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="bf1c1-134">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="bf1c1-134">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

