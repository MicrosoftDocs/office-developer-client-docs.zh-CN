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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 202d461d4acefe18e69b47db9319cb328c61406e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592316"
---
# <a name="imapiviewadvisesinkonprint"></a><span data-ttu-id="8be20-103">IMAPIViewAdviseSink::OnPrint</span><span class="sxs-lookup"><span data-stu-id="8be20-103">IMAPIViewAdviseSink::OnPrint</span></span>

  
  
<span data-ttu-id="8be20-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8be20-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8be20-105">通知窗体的打印状态的表单查看器。</span><span class="sxs-lookup"><span data-stu-id="8be20-105">Notifies the form viewer of the printing status of a form.</span></span>
  
```cpp
HRESULT OnPrint(
ULONG dwPageNumber,
HRESULT hrStatus
);
```

## <a name="parameters"></a><span data-ttu-id="8be20-106">参数</span><span class="sxs-lookup"><span data-stu-id="8be20-106">Parameters</span></span>

 <span data-ttu-id="8be20-107">_dwPageNumber_</span><span class="sxs-lookup"><span data-stu-id="8be20-107">_dwPageNumber_</span></span>
  
> <span data-ttu-id="8be20-108">[in]数的最后一页打印。</span><span class="sxs-lookup"><span data-stu-id="8be20-108">[in] Number of the last page printed.</span></span>
    
 <span data-ttu-id="8be20-109">_hrStatus_</span><span class="sxs-lookup"><span data-stu-id="8be20-109">_hrStatus_</span></span>
  
> <span data-ttu-id="8be20-110">[in]指示打印作业的状态的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="8be20-110">[in] An HRESULT value indicating the status of the print job.</span></span> <span data-ttu-id="8be20-111">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="8be20-111">Possible values are:</span></span>
    
<span data-ttu-id="8be20-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8be20-112">S_FALSE</span></span> 
  
> <span data-ttu-id="8be20-113">打印作业已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8be20-113">The printing job has finished successfully.</span></span>
    
<span data-ttu-id="8be20-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8be20-114">S_OK</span></span> 
  
> <span data-ttu-id="8be20-115">打印作业正在运行。</span><span class="sxs-lookup"><span data-stu-id="8be20-115">The printing job is in progress.</span></span>
    
<span data-ttu-id="8be20-116">失败</span><span class="sxs-lookup"><span data-stu-id="8be20-116">FAILED</span></span> 
  
> <span data-ttu-id="8be20-117">打印作业已终止由于失败而导致。</span><span class="sxs-lookup"><span data-stu-id="8be20-117">The printing job was terminated due to a failure.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8be20-118">返回值</span><span class="sxs-lookup"><span data-stu-id="8be20-118">Return value</span></span>

<span data-ttu-id="8be20-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8be20-119">S_OK</span></span> 
  
> <span data-ttu-id="8be20-120">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="8be20-120">The notification succeeded.</span></span>
    
<span data-ttu-id="8be20-121">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="8be20-121">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="8be20-122">用户取消操作，通常通过单击对话框中的取消按钮。</span><span class="sxs-lookup"><span data-stu-id="8be20-122">The user canceled the operation, typically by clicking the Cancel button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8be20-123">注解</span><span class="sxs-lookup"><span data-stu-id="8be20-123">Remarks</span></span>

<span data-ttu-id="8be20-124">表单对象调用**IMAPIViewAdviseSink::OnPrint**方法时打印，告知打印进度的查看器。</span><span class="sxs-lookup"><span data-stu-id="8be20-124">Form objects call the **IMAPIViewAdviseSink::OnPrint** method while printing to inform the viewer of printing progress.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8be20-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8be20-125">Notes to callers</span></span>

<span data-ttu-id="8be20-126">如果打印作业涉及多个页面，则可以呼叫**OnPrint**后每一页打印。</span><span class="sxs-lookup"><span data-stu-id="8be20-126">If the printing job involves multiple pages, you can call **OnPrint** after each page is printed.</span></span> <span data-ttu-id="8be20-127">将_dwPageNumber_到当前打印页面和_hrStatus_设置为返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8be20-127">Set  _dwPageNumber_ to the page currently being printed and  _hrStatus_ to S_OK.</span></span> <span data-ttu-id="8be20-128">打印作业完成时，呼叫与_dwPageNumber_ **OnPrint**设置到最后一页打印和_hrStatus_将设置为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="8be20-128">When the printing job is complete, call **OnPrint** with  _dwPageNumber_ set to the last page printed and  _hrStatus_ set to S_FALSE.</span></span> 
  
<span data-ttu-id="8be20-129">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="8be20-129">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8be20-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8be20-130">See also</span></span>



[<span data-ttu-id="8be20-131">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8be20-131">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

