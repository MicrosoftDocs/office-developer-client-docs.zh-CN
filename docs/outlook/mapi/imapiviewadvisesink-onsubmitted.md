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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ebde06d0d22320ecb5edb633cf8d04aaeec2a841
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433981"
---
# <a name="imapiviewadvisesinkonsubmitted"></a><span data-ttu-id="a15c5-103">IMAPIViewAdviseSink::OnSubmitted</span><span class="sxs-lookup"><span data-stu-id="a15c5-103">IMAPIViewAdviseSink::OnSubmitted</span></span>

  
  
<span data-ttu-id="a15c5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a15c5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a15c5-105">通知表单查看器当前邮件已提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="a15c5-105">Notifies the form viewer that the current message has been submitted to the MAPI spooler.</span></span>
  
```cpp
HRESULT OnSubmitted( void );
```

## <a name="parameters"></a><span data-ttu-id="a15c5-106">参数</span><span class="sxs-lookup"><span data-stu-id="a15c5-106">Parameters</span></span>

<span data-ttu-id="a15c5-107">无</span><span class="sxs-lookup"><span data-stu-id="a15c5-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="a15c5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a15c5-108">Return value</span></span>

<span data-ttu-id="a15c5-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a15c5-109">S_OK</span></span> 
  
> <span data-ttu-id="a15c5-110">通知成功。</span><span class="sxs-lookup"><span data-stu-id="a15c5-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a15c5-111">备注</span><span class="sxs-lookup"><span data-stu-id="a15c5-111">Remarks</span></span>

<span data-ttu-id="a15c5-112">表单对象在调用 [IMAPIMessageSite：：SubmitMessage](imapimessagesite-submitmessage.md)成功后调用 **IMAPIViewAdviseSink：：OnSubmitted** 方法。</span><span class="sxs-lookup"><span data-stu-id="a15c5-112">A form object calls the **IMAPIViewAdviseSink::OnSubmitted** method after a call to [IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md) has returned successfully.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a15c5-113">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a15c5-113">Notes to implementers</span></span>

<span data-ttu-id="a15c5-114">调用 **OnSubmitted** 后，可以继续假定邮件已更新。</span><span class="sxs-lookup"><span data-stu-id="a15c5-114">After **OnSubmitted** is called, you can continue on the assumption that the message has been updated.</span></span> <span data-ttu-id="a15c5-115">更新窗口以反映已发生的任何更改。</span><span class="sxs-lookup"><span data-stu-id="a15c5-115">Update your windows to reflect any changes that have occurred.</span></span> 
  
<span data-ttu-id="a15c5-116">有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="a15c5-116">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a15c5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a15c5-117">See also</span></span>



[<span data-ttu-id="a15c5-118">IMAPIMessageSite::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="a15c5-118">IMAPIMessageSite::SubmitMessage</span></span>](imapimessagesite-submitmessage.md)
  
[<span data-ttu-id="a15c5-119">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a15c5-119">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

