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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ec78331fd013777f001d39bd7e978a67abb5342
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407604"
---
# <a name="imapiviewadvisesinkonsaved"></a><span data-ttu-id="bceab-103">IMAPIViewAdviseSink::OnSaved</span><span class="sxs-lookup"><span data-stu-id="bceab-103">IMAPIViewAdviseSink::OnSaved</span></span>

  
  
<span data-ttu-id="bceab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bceab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bceab-105">通知窗体查看器窗体中的当前邮件已保存。</span><span class="sxs-lookup"><span data-stu-id="bceab-105">Notifies the form viewer that the current message in a form has been saved.</span></span>
  
```cpp
HRESULT OnSaved( void );
```

## <a name="parameters"></a><span data-ttu-id="bceab-106">参数</span><span class="sxs-lookup"><span data-stu-id="bceab-106">Parameters</span></span>

<span data-ttu-id="bceab-107">无</span><span class="sxs-lookup"><span data-stu-id="bceab-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="bceab-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bceab-108">Return value</span></span>

<span data-ttu-id="bceab-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="bceab-109">S_OK</span></span> 
  
> <span data-ttu-id="bceab-110">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="bceab-110">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bceab-111">备注</span><span class="sxs-lookup"><span data-stu-id="bceab-111">Remarks</span></span>

<span data-ttu-id="bceab-112">表单对象在成功保存表单中的当前邮件后调用 **IMAPIViewAdviseSink：：OnSaved** 方法。</span><span class="sxs-lookup"><span data-stu-id="bceab-112">A form object calls the **IMAPIViewAdviseSink::OnSaved** method after the current message in a form has been successfully saved.</span></span> <span data-ttu-id="bceab-113">这样，查看者可以更新其窗口以反映对邮件的更改。</span><span class="sxs-lookup"><span data-stu-id="bceab-113">Doing so permits viewers to update their windows to reflect changes to the message.</span></span> 
  
<span data-ttu-id="bceab-114">有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="bceab-114">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bceab-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bceab-115">See also</span></span>



[<span data-ttu-id="bceab-116">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bceab-116">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

