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
ms.openlocfilehash: 0f9aa5d508afeaf5933c50763e1e42832ae4e3f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775741"
---
# <a name="imapiviewadvisesinkonsaved"></a><span data-ttu-id="e31c2-103">IMAPIViewAdviseSink::OnSaved</span><span class="sxs-lookup"><span data-stu-id="e31c2-103">IMAPIViewAdviseSink::OnSaved</span></span>

  
  
<span data-ttu-id="e31c2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e31c2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e31c2-105">通知已保存窗体中的当前消息表单查看器。</span><span class="sxs-lookup"><span data-stu-id="e31c2-105">Notifies the form viewer that the current message in a form has been saved.</span></span>
  
```cpp
HRESULT OnSaved( void );
```

## <a name="parameters"></a><span data-ttu-id="e31c2-106">参数</span><span class="sxs-lookup"><span data-stu-id="e31c2-106">Parameters</span></span>

<span data-ttu-id="e31c2-107">无</span><span class="sxs-lookup"><span data-stu-id="e31c2-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="e31c2-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e31c2-108">Return value</span></span>

<span data-ttu-id="e31c2-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e31c2-109">S_OK</span></span> 
  
> <span data-ttu-id="e31c2-110">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="e31c2-110">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e31c2-111">说明</span><span class="sxs-lookup"><span data-stu-id="e31c2-111">Remarks</span></span>

<span data-ttu-id="e31c2-112">Form 对象调用**IMAPIViewAdviseSink::OnSaved**方法后已成功保存窗体中的当前消息。</span><span class="sxs-lookup"><span data-stu-id="e31c2-112">A form object calls the **IMAPIViewAdviseSink::OnSaved** method after the current message in a form has been successfully saved.</span></span> <span data-ttu-id="e31c2-113">这样就可以查看器更新以反映邮件及其窗口。</span><span class="sxs-lookup"><span data-stu-id="e31c2-113">Doing so permits viewers to update their windows to reflect changes to the message.</span></span> 
  
<span data-ttu-id="e31c2-114">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="e31c2-114">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e31c2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e31c2-115">See also</span></span>



[<span data-ttu-id="e31c2-116">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e31c2-116">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

