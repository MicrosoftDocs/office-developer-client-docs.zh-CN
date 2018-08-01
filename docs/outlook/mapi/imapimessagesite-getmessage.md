---
title: IMAPIMessageSiteGetMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetMessage
api_type:
- COM
ms.assetid: 49d12c49-84f8-44ac-bc4a-2ee44a46f8c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3cdd9994de3e2a02a5302068881abce57a632a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775455"
---
# <a name="imapimessagesitegetmessage"></a><span data-ttu-id="4e80c-103">IMAPIMessageSite::GetMessage</span><span class="sxs-lookup"><span data-stu-id="4e80c-103">IMAPIMessageSite::GetMessage</span></span>

  
  
<span data-ttu-id="4e80c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4e80c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4e80c-105">返回当前邮件。</span><span class="sxs-lookup"><span data-stu-id="4e80c-105">Returns the current message.</span></span>
  
```cpp
HRESULT GetMessage(
  LPMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a><span data-ttu-id="4e80c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4e80c-106">Parameters</span></span>

 <span data-ttu-id="4e80c-107">_ppmsg_</span><span class="sxs-lookup"><span data-stu-id="4e80c-107">_ppmsg_</span></span>
  
> <span data-ttu-id="4e80c-108">[输出]指向的邮件返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="4e80c-108">[out] A pointer to a pointer to the returned interface for the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4e80c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4e80c-109">Return value</span></span>

<span data-ttu-id="4e80c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e80c-110">S_OK</span></span> 
  
> <span data-ttu-id="4e80c-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="4e80c-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="4e80c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4e80c-112">S_FALSE</span></span> 
  
> <span data-ttu-id="4e80c-113">调用窗体的当前不存在任何消息。</span><span class="sxs-lookup"><span data-stu-id="4e80c-113">No message currently exists for the calling form.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4e80c-114">说明</span><span class="sxs-lookup"><span data-stu-id="4e80c-114">Remarks</span></span>

<span data-ttu-id="4e80c-115">窗体调用**IMAPIMessageSite::GetMessage**方法获取当前消息的消息界面。</span><span class="sxs-lookup"><span data-stu-id="4e80c-115">Forms call the **IMAPIMessageSite::GetMessage** method to obtain a message interface for the current message.</span></span> <span data-ttu-id="4e80c-116">当前消息是相同的消息，如以前[IPersistMessage::InitNew](ipersistmessage-initnew.md)、 [IPersistMessage::Load](ipersistmessage-load.md)或[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法中传递。</span><span class="sxs-lookup"><span data-stu-id="4e80c-116">The current message is the same message as was previously passed in the [IPersistMessage::InitNew](ipersistmessage-initnew.md), [IPersistMessage::Load](ipersistmessage-load.md), or [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method.</span></span> 
  
 <span data-ttu-id="4e80c-117">如果当前不存在任何消息， **GetMessage**返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="4e80c-117">**GetMessage** returns S_FALSE if no message currently exists.</span></span> <span data-ttu-id="4e80c-118">[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法或**IPersistMessage::Load**到下一个呼叫之前呼叫后可能出现此状态或进行**IPersistMessage::SaveCompleted** 。</span><span class="sxs-lookup"><span data-stu-id="4e80c-118">This state can occur after calls to the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method or before the next call to **IPersistMessage::Load** or **IPersistMessage::SaveCompleted** is made.</span></span> 
  
<span data-ttu-id="4e80c-119">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="4e80c-119">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="4e80c-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="4e80c-120">MFCMAPI reference</span></span>

<span data-ttu-id="4e80c-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="4e80c-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="4e80c-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="4e80c-122">**File**</span></span>|<span data-ttu-id="4e80c-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="4e80c-123">**Function**</span></span>|<span data-ttu-id="4e80c-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4e80c-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4e80c-125">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="4e80c-125">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="4e80c-126">CMyMAPIFormViewer::GetSession</span><span class="sxs-lookup"><span data-stu-id="4e80c-126">CMyMAPIFormViewer::GetSession</span></span>  <br/> |<span data-ttu-id="4e80c-127">MFCMAPI 使用**IMAPIMessageSite::GetMessage**方法可返回当前缓存的邮件指针，它是否可用。</span><span class="sxs-lookup"><span data-stu-id="4e80c-127">MFCMAPI uses the **IMAPIMessageSite::GetMessage** method to return the currently cached message pointer, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4e80c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e80c-128">See also</span></span>



[<span data-ttu-id="4e80c-129">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="4e80c-129">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="4e80c-130">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="4e80c-130">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md)
  
[<span data-ttu-id="4e80c-131">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4e80c-131">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="4e80c-132">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="4e80c-132">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="4e80c-133">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="4e80c-133">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="4e80c-134">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4e80c-134">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="4e80c-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="4e80c-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="4e80c-136">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="4e80c-136">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

