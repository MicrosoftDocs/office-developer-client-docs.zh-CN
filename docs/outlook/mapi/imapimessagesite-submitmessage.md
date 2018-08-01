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
ms.openlocfilehash: 694ee8b12b9918502e60c0c6ea92992cc1062945
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775475"
---
# <a name="imapimessagesitesubmitmessage"></a><span data-ttu-id="240ed-103">IMAPIMessageSite::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="240ed-103">IMAPIMessageSite::SubmitMessage</span></span>

  
  
<span data-ttu-id="240ed-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="240ed-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="240ed-105">当前邮件在排队等待传送的请求。</span><span class="sxs-lookup"><span data-stu-id="240ed-105">Requests that the current message be queued for delivery.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="240ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="240ed-106">Parameters</span></span>

 <span data-ttu-id="240ed-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="240ed-107">_ulFlags_</span></span>
  
> <span data-ttu-id="240ed-108">[in]位掩码的标志，控制如何提交一条消息。</span><span class="sxs-lookup"><span data-stu-id="240ed-108">[in] A bitmask of flags that controls how a message is submitted.</span></span> <span data-ttu-id="240ed-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="240ed-109">The following flag can be set:</span></span>
    
<span data-ttu-id="240ed-110">FORCE_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="240ed-110">FORCE_SUBMIT</span></span> 
  
> <span data-ttu-id="240ed-111">MAPI 应提交的邮件，即使它可能不立即发送。</span><span class="sxs-lookup"><span data-stu-id="240ed-111">MAPI should submit the message even if it might not be sent immediately.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="240ed-112">返回值</span><span class="sxs-lookup"><span data-stu-id="240ed-112">Return value</span></span>

<span data-ttu-id="240ed-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="240ed-113">S_OK</span></span> 
  
> <span data-ttu-id="240ed-114">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="240ed-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="240ed-115">说明</span><span class="sxs-lookup"><span data-stu-id="240ed-115">Remarks</span></span>

<span data-ttu-id="240ed-116">表单对象调用**IMAPIMessageSite::SubmitMessage**方法以请求邮件在排队等待传送。</span><span class="sxs-lookup"><span data-stu-id="240ed-116">Form objects call the **IMAPIMessageSite::SubmitMessage** method to request that a message be queued for delivery.</span></span> <span data-ttu-id="240ed-117">消息网站应在提交邮件之前调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="240ed-117">The message site should call the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method before submitting the message.</span></span> <span data-ttu-id="240ed-118">消息不需要已以前保存，因为**SubmitMessage**应会导致如果已修改邮件同时保存邮件。</span><span class="sxs-lookup"><span data-stu-id="240ed-118">The message does not need to have been previously saved, because **SubmitMessage** should cause the message to be saved if the message has been modified.</span></span> <span data-ttu-id="240ed-119">后**SubmitMessage**返回时，窗体必须检查当前消息，然后关闭本身，如果不存在。</span><span class="sxs-lookup"><span data-stu-id="240ed-119">After the return of **SubmitMessage**, the form must check for a current message and then dismiss itself if none exists.</span></span> 
  
<span data-ttu-id="240ed-120">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="240ed-120">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="240ed-121">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="240ed-121">MFCMAPI reference</span></span>

<span data-ttu-id="240ed-122">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="240ed-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="240ed-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="240ed-123">**File**</span></span>|<span data-ttu-id="240ed-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="240ed-124">**Function**</span></span>|<span data-ttu-id="240ed-125">**Comment**</span><span class="sxs-lookup"><span data-stu-id="240ed-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="240ed-126">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="240ed-126">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="240ed-127">CMyMAPIFormViewer::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="240ed-127">CMyMAPIFormViewer::SubmitMessage</span></span>  <br/> |<span data-ttu-id="240ed-128">MFCMAPI 使用**IMAPIMessageSite::SubmitMessage**方法保存邮件。</span><span class="sxs-lookup"><span data-stu-id="240ed-128">MFCMAPI uses the **IMAPIMessageSite::SubmitMessage** method to save the message.</span></span> <span data-ttu-id="240ed-129">首先，它将调用**IPersistMessage::HandsOffMessage**方法，然后它调用**SubmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="240ed-129">First, it calls the **IPersistMessage::HandsOffMessage** method, and then it calls **SubmitMessage**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="240ed-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="240ed-130">See also</span></span>



[<span data-ttu-id="240ed-131">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="240ed-131">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="240ed-132">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="240ed-132">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="240ed-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="240ed-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="240ed-134">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="240ed-134">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

