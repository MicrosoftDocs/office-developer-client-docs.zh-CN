---
title: IMAPIViewAdviseSinkOnSubmitted
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnSubmitted
api_type:
- COM
ms.assetid: a2401662-1ddc-40d8-a5a7-ceca24442bd4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 40a72bed0b3e763ea482b228174b85d9f42185c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775728"
---
# <a name="imapiviewadvisesinkonsubmitted"></a><span data-ttu-id="ff313-103">IMAPIViewAdviseSink::OnSubmitted</span><span class="sxs-lookup"><span data-stu-id="ff313-103">IMAPIViewAdviseSink::OnSubmitted</span></span>

  
  
<span data-ttu-id="ff313-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff313-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff313-105">通知表单查看器的当前消息，已提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ff313-105">Notifies the form viewer that the current message has been submitted to the MAPI spooler.</span></span>
  
```cpp
HRESULT OnSubmitted( void );
```

## <a name="parameters"></a><span data-ttu-id="ff313-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff313-106">Parameters</span></span>

<span data-ttu-id="ff313-107">无</span><span class="sxs-lookup"><span data-stu-id="ff313-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="ff313-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ff313-108">Return value</span></span>

<span data-ttu-id="ff313-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff313-109">S_OK</span></span> 
  
> <span data-ttu-id="ff313-110">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="ff313-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff313-111">说明</span><span class="sxs-lookup"><span data-stu-id="ff313-111">Remarks</span></span>

<span data-ttu-id="ff313-112">Form 对象调用**IMAPIViewAdviseSink::OnSubmitted**方法对[IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md)的调用返回了成功之后。</span><span class="sxs-lookup"><span data-stu-id="ff313-112">A form object calls the **IMAPIViewAdviseSink::OnSubmitted** method after a call to [IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md) has returned successfully.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="ff313-113">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="ff313-113">Notes to implementers</span></span>

<span data-ttu-id="ff313-114">调用**OnSubmitted**后，您可以继续在假设邮件已更新。</span><span class="sxs-lookup"><span data-stu-id="ff313-114">After **OnSubmitted** is called, you can continue on the assumption that the message has been updated.</span></span> <span data-ttu-id="ff313-115">更新您的 windows，以反映发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="ff313-115">Update your windows to reflect any changes that have occurred.</span></span> 
  
<span data-ttu-id="ff313-116">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="ff313-116">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff313-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff313-117">See also</span></span>



[<span data-ttu-id="ff313-118">IMAPIMessageSite::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="ff313-118">IMAPIMessageSite::SubmitMessage</span></span>](imapimessagesite-submitmessage.md)
  
[<span data-ttu-id="ff313-119">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ff313-119">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

