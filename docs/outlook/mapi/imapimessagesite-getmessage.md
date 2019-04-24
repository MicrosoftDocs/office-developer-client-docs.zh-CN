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
ms.openlocfilehash: 03dd0553d0203585850ac5c4f8c91c86ef60236a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321278"
---
# <a name="imapimessagesitegetmessage"></a><span data-ttu-id="90d2b-103">IMAPIMessageSite::GetMessage</span><span class="sxs-lookup"><span data-stu-id="90d2b-103">IMAPIMessageSite::GetMessage</span></span>

  
  
<span data-ttu-id="90d2b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90d2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90d2b-105">返回当前邮件。</span><span class="sxs-lookup"><span data-stu-id="90d2b-105">Returns the current message.</span></span>
  
```cpp
HRESULT GetMessage(
  LPMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a><span data-ttu-id="90d2b-106">参数</span><span class="sxs-lookup"><span data-stu-id="90d2b-106">Parameters</span></span>

 <span data-ttu-id="90d2b-107">_ppmsg_</span><span class="sxs-lookup"><span data-stu-id="90d2b-107">_ppmsg_</span></span>
  
> <span data-ttu-id="90d2b-108">排除指向指向邮件的返回接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="90d2b-108">[out] A pointer to a pointer to the returned interface for the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="90d2b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="90d2b-109">Return value</span></span>

<span data-ttu-id="90d2b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="90d2b-110">S_OK</span></span> 
  
> <span data-ttu-id="90d2b-111">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="90d2b-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="90d2b-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="90d2b-112">S_FALSE</span></span> 
  
> <span data-ttu-id="90d2b-113">当前没有适用于通话窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="90d2b-113">No message currently exists for the calling form.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="90d2b-114">注解</span><span class="sxs-lookup"><span data-stu-id="90d2b-114">Remarks</span></span>

<span data-ttu-id="90d2b-115">窗体调用**IMAPIMessageSite:: GetMessage**方法来获取当前邮件的消息接口。</span><span class="sxs-lookup"><span data-stu-id="90d2b-115">Forms call the **IMAPIMessageSite::GetMessage** method to obtain a message interface for the current message.</span></span> <span data-ttu-id="90d2b-116">当前邮件与以前在[IPersistMessage:: InitNew](ipersistmessage-initnew.md), [IPersistMessage:: Load](ipersistmessage-load.md)或[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)方法中传递的邮件相同。</span><span class="sxs-lookup"><span data-stu-id="90d2b-116">The current message is the same message as was previously passed in the [IPersistMessage::InitNew](ipersistmessage-initnew.md), [IPersistMessage::Load](ipersistmessage-load.md), or [IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md) method.</span></span> 
  
 <span data-ttu-id="90d2b-117">如果当前不存在邮件, **GetMessage**将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="90d2b-117">**GetMessage** returns S_FALSE if no message currently exists.</span></span> <span data-ttu-id="90d2b-118">在调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)方法之前, 或在下一次调用**IPersistMessage:: Load** or **IPersistMessage:: SaveCompleted**之前, 可能会发生此状态。</span><span class="sxs-lookup"><span data-stu-id="90d2b-118">This state can occur after calls to the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method or before the next call to **IPersistMessage::Load** or **IPersistMessage::SaveCompleted** is made.</span></span> 
  
<span data-ttu-id="90d2b-119">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="90d2b-119">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="90d2b-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="90d2b-120">MFCMAPI reference</span></span>

<span data-ttu-id="90d2b-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="90d2b-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="90d2b-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="90d2b-122">**File**</span></span>|<span data-ttu-id="90d2b-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="90d2b-123">**Function**</span></span>|<span data-ttu-id="90d2b-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="90d2b-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90d2b-125">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="90d2b-125">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="90d2b-126">CMyMAPIFormViewer:: GetSession</span><span class="sxs-lookup"><span data-stu-id="90d2b-126">CMyMAPIFormViewer::GetSession</span></span>  <br/> |<span data-ttu-id="90d2b-127">MFCMAPI 使用**IMAPIMessageSite:: GetMessage**方法返回当前缓存的邮件指针 (如果可用)。</span><span class="sxs-lookup"><span data-stu-id="90d2b-127">MFCMAPI uses the **IMAPIMessageSite::GetMessage** method to return the currently cached message pointer, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="90d2b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90d2b-128">See also</span></span>



[<span data-ttu-id="90d2b-129">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="90d2b-129">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md)
  
[<span data-ttu-id="90d2b-130">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="90d2b-130">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md)
  
[<span data-ttu-id="90d2b-131">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="90d2b-131">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="90d2b-132">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="90d2b-132">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="90d2b-133">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="90d2b-133">IPersistMessage::SaveCompleted</span></span>](ipersistmessage-savecompleted.md)
  
[<span data-ttu-id="90d2b-134">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="90d2b-134">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="90d2b-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="90d2b-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="90d2b-136">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="90d2b-136">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

