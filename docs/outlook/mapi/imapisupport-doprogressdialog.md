---
title: IMAPISupportDoProgressDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoProgressDialog
api_type:
- COM
ms.assetid: 74c52b96-e903-444b-8bda-73a08f278c22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3de29e9af5caa82d2e57c8fcbbdab7d5ddb19dd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432581"
---
# <a name="imapisupportdoprogressdialog"></a><span data-ttu-id="f14f5-103">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="f14f5-103">IMAPISupport::DoProgressDialog</span></span>

  
  
<span data-ttu-id="f14f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f14f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f14f5-105">检索显示进度指示器的进度对象。</span><span class="sxs-lookup"><span data-stu-id="f14f5-105">Retrieves a progress object that displays a progress indicator.</span></span>
  
```cpp
HRESULT DoProgressDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIPROGRESS FAR * lppProgress
);
```

## <a name="parameters"></a><span data-ttu-id="f14f5-106">参数</span><span class="sxs-lookup"><span data-stu-id="f14f5-106">Parameters</span></span>

 <span data-ttu-id="f14f5-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="f14f5-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="f14f5-108">实时进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="f14f5-108">[in] A handle to the parent window of the progress indicator.</span></span>
    
 <span data-ttu-id="f14f5-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f14f5-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f14f5-110">实时标志的位掩码, 用于控制进度对象应如何计算进度。</span><span class="sxs-lookup"><span data-stu-id="f14f5-110">[in] A bitmask of flags that controls how the progress object should calculate progress.</span></span> <span data-ttu-id="f14f5-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="f14f5-111">The following flag can be set:</span></span>
    
<span data-ttu-id="f14f5-112">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="f14f5-112">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="f14f5-113">对顶级项目 (如父文件夹) 的进度进行计算。</span><span class="sxs-lookup"><span data-stu-id="f14f5-113">Progress is calculated for a top-level item, such as a parent folder.</span></span> <span data-ttu-id="f14f5-114">进度对象应使用[IMAPIProgress::P rogress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数中的值, 它们分别指示当前项和操作中的项目总数, 以增加进度操作的指示器。</span><span class="sxs-lookup"><span data-stu-id="f14f5-114">The progress object should use the values in the [IMAPIProgress::Progress](imapiprogress-progress.md) method's  _ulCount_ and  _ulTotal_ parameters — which indicate the current item and the total items in the operation, respectively — to increment the progress indicator for the operation.</span></span> 
    
 <span data-ttu-id="f14f5-115">_lppProgress_</span><span class="sxs-lookup"><span data-stu-id="f14f5-115">_lppProgress_</span></span>
  
> <span data-ttu-id="f14f5-116">排除指向进度对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f14f5-116">[out] A pointer to a pointer to the progress object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f14f5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="f14f5-117">Return value</span></span>

<span data-ttu-id="f14f5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f14f5-118">S_OK</span></span> 
  
> <span data-ttu-id="f14f5-119">已成功检索进度对象。</span><span class="sxs-lookup"><span data-stu-id="f14f5-119">The progress object was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f14f5-120">说明</span><span class="sxs-lookup"><span data-stu-id="f14f5-120">Remarks</span></span>

<span data-ttu-id="f14f5-121">**IMAPISupport::D oprogressdialog**方法是为通讯簿和邮件存储提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="f14f5-121">The **IMAPISupport::DoProgressDialog** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="f14f5-122">这些提供程序调用**DoProgressDialog**以访问[IMAPIProgress](imapiprogressiunknown.md)接口的 MAPI 实现, 这将计算进度信息并显示标准对话框。</span><span class="sxs-lookup"><span data-stu-id="f14f5-122">These providers call **DoProgressDialog** to access the MAPI implementation of the [IMAPIProgress](imapiprogressiunknown.md) interface, which calculates the progress information and displays a standard dialog box.</span></span> 
  
<span data-ttu-id="f14f5-123">有关如何使用进度对象和**IMAPIProgress**接口的信息, 请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="f14f5-123">For information about how to use a progress object and the **IMAPIProgress** interface, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f14f5-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f14f5-124">See also</span></span>



[<span data-ttu-id="f14f5-125">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f14f5-125">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="f14f5-126">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="f14f5-126">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="f14f5-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f14f5-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="f14f5-128">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="f14f5-128">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)

