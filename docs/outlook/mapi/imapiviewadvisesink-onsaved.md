---
title: IMAPIViewAdviseSinkOnSaved
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnSaved
api_type:
- COM
ms.assetid: c327e31a-7b62-4e21-9b69-b27442f1eaca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ae94b40d984adee0f3c888f69dfdbffb1e352e1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584434"
---
# <a name="imapiviewadvisesinkonsaved"></a><span data-ttu-id="925cf-103">IMAPIViewAdviseSink::OnSaved</span><span class="sxs-lookup"><span data-stu-id="925cf-103">IMAPIViewAdviseSink::OnSaved</span></span>

  
  
<span data-ttu-id="925cf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="925cf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="925cf-105">通知已保存窗体中的当前消息表单查看器。</span><span class="sxs-lookup"><span data-stu-id="925cf-105">Notifies the form viewer that the current message in a form has been saved.</span></span>
  
```cpp
HRESULT OnSaved( void );
```

## <a name="parameters"></a><span data-ttu-id="925cf-106">参数</span><span class="sxs-lookup"><span data-stu-id="925cf-106">Parameters</span></span>

<span data-ttu-id="925cf-107">无</span><span class="sxs-lookup"><span data-stu-id="925cf-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="925cf-108">返回值</span><span class="sxs-lookup"><span data-stu-id="925cf-108">Return value</span></span>

<span data-ttu-id="925cf-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="925cf-109">S_OK</span></span> 
  
> <span data-ttu-id="925cf-110">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="925cf-110">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="925cf-111">注解</span><span class="sxs-lookup"><span data-stu-id="925cf-111">Remarks</span></span>

<span data-ttu-id="925cf-112">Form 对象调用**IMAPIViewAdviseSink::OnSaved**方法后已成功保存窗体中的当前消息。</span><span class="sxs-lookup"><span data-stu-id="925cf-112">A form object calls the **IMAPIViewAdviseSink::OnSaved** method after the current message in a form has been successfully saved.</span></span> <span data-ttu-id="925cf-113">这样就可以查看器更新以反映邮件及其窗口。</span><span class="sxs-lookup"><span data-stu-id="925cf-113">Doing so permits viewers to update their windows to reflect changes to the message.</span></span> 
  
<span data-ttu-id="925cf-114">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="925cf-114">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="925cf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="925cf-115">See also</span></span>



[<span data-ttu-id="925cf-116">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="925cf-116">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

