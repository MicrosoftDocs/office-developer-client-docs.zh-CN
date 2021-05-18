---
title: IMAPIViewAdviseSinkOnPrint
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnPrint
api_type:
- COM
ms.assetid: d16219a0-268c-428d-9f02-4f06eb5b6d7d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e66315042f8b5cd5aff0e4aa076588c9f312376a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406169"
---
# <a name="imapiviewadvisesinkonprint"></a><span data-ttu-id="ca8bc-103">IMAPIViewAdviseSink::OnPrint</span><span class="sxs-lookup"><span data-stu-id="ca8bc-103">IMAPIViewAdviseSink::OnPrint</span></span>

  
  
<span data-ttu-id="ca8bc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca8bc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca8bc-105">通知窗体查看者窗体的打印状态。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-105">Notifies the form viewer of the printing status of a form.</span></span>
  
```cpp
HRESULT OnPrint(
ULONG dwPageNumber,
HRESULT hrStatus
);
```

## <a name="parameters"></a><span data-ttu-id="ca8bc-106">参数</span><span class="sxs-lookup"><span data-stu-id="ca8bc-106">Parameters</span></span>

 <span data-ttu-id="ca8bc-107">_dwPageNumber_</span><span class="sxs-lookup"><span data-stu-id="ca8bc-107">_dwPageNumber_</span></span>
  
> <span data-ttu-id="ca8bc-108">[in]打印的最后一页的页码。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-108">[in] Number of the last page printed.</span></span>
    
 <span data-ttu-id="ca8bc-109">_hrStatus_</span><span class="sxs-lookup"><span data-stu-id="ca8bc-109">_hrStatus_</span></span>
  
> <span data-ttu-id="ca8bc-110">[in]一个 HRESULT 值，指示打印作业的状态。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-110">[in] An HRESULT value indicating the status of the print job.</span></span> <span data-ttu-id="ca8bc-111">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="ca8bc-111">Possible values are:</span></span>
    
<span data-ttu-id="ca8bc-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ca8bc-112">S_FALSE</span></span> 
  
> <span data-ttu-id="ca8bc-113">打印作业已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-113">The printing job has finished successfully.</span></span>
    
<span data-ttu-id="ca8bc-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca8bc-114">S_OK</span></span> 
  
> <span data-ttu-id="ca8bc-115">打印作业正在进行中。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-115">The printing job is in progress.</span></span>
    
<span data-ttu-id="ca8bc-116">FAILED</span><span class="sxs-lookup"><span data-stu-id="ca8bc-116">FAILED</span></span> 
  
> <span data-ttu-id="ca8bc-117">打印作业由于失败而终止。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-117">The printing job was terminated due to a failure.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ca8bc-118">返回值</span><span class="sxs-lookup"><span data-stu-id="ca8bc-118">Return value</span></span>

<span data-ttu-id="ca8bc-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca8bc-119">S_OK</span></span> 
  
> <span data-ttu-id="ca8bc-120">通知成功。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-120">The notification succeeded.</span></span>
    
<span data-ttu-id="ca8bc-121">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ca8bc-121">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="ca8bc-122">用户通常通过单击对话框中的"取消"按钮来取消操作。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-122">The user canceled the operation, typically by clicking the Cancel button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ca8bc-123">备注</span><span class="sxs-lookup"><span data-stu-id="ca8bc-123">Remarks</span></span>

<span data-ttu-id="ca8bc-124">Form 对象在打印时调用 **IMAPIViewAdviseSink：：OnPrint** 方法，以通知查看者打印进度。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-124">Form objects call the **IMAPIViewAdviseSink::OnPrint** method while printing to inform the viewer of printing progress.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ca8bc-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ca8bc-125">Notes to callers</span></span>

<span data-ttu-id="ca8bc-126">如果打印作业涉及多个页面，您可以在打印每个页面后调用 **OnPrint。**</span><span class="sxs-lookup"><span data-stu-id="ca8bc-126">If the printing job involves multiple pages, you can call **OnPrint** after each page is printed.</span></span> <span data-ttu-id="ca8bc-127">将  _dwPageNumber_ 设置为当前正在打印的页面，将  _hrStatus_ 设置为S_OK。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-127">Set  _dwPageNumber_ to the page currently being printed and  _hrStatus_ to S_OK.</span></span> <span data-ttu-id="ca8bc-128">打印作业完成后，调用 **OnPrint，** 将  _dwPageNumber_ 设置为打印的最后一页，  _将 hrStatus_ 设置为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-128">When the printing job is complete, call **OnPrint** with  _dwPageNumber_ set to the last page printed and  _hrStatus_ set to S_FALSE.</span></span> 
  
<span data-ttu-id="ca8bc-129">有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="ca8bc-129">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca8bc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca8bc-130">See also</span></span>



[<span data-ttu-id="ca8bc-131">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ca8bc-131">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

