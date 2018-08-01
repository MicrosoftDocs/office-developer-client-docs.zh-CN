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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 527a7bb3201a4a6b1bc0807136bc88b80c189de2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775621"
---
# <a name="imapisupportdoprogressdialog"></a><span data-ttu-id="9abc3-103">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="9abc3-103">IMAPISupport::DoProgressDialog</span></span>

  
  
<span data-ttu-id="9abc3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9abc3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9abc3-105">检索一个进度对象，它显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="9abc3-105">Retrieves a progress object that displays a progress indicator.</span></span>
  
```cpp
HRESULT DoProgressDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIPROGRESS FAR * lppProgress
);
```

## <a name="parameters"></a><span data-ttu-id="9abc3-106">参数</span><span class="sxs-lookup"><span data-stu-id="9abc3-106">Parameters</span></span>

 <span data-ttu-id="9abc3-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9abc3-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="9abc3-108">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="9abc3-108">[in] A handle to the parent window of the progress indicator.</span></span>
    
 <span data-ttu-id="9abc3-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9abc3-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9abc3-110">[in]位掩码的标志的控件的进度对象应如何计算进度。</span><span class="sxs-lookup"><span data-stu-id="9abc3-110">[in] A bitmask of flags that controls how the progress object should calculate progress.</span></span> <span data-ttu-id="9abc3-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="9abc3-111">The following flag can be set:</span></span>
    
<span data-ttu-id="9abc3-112">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="9abc3-112">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="9abc3-113">顶级项目，如父文件夹计算进度。</span><span class="sxs-lookup"><span data-stu-id="9abc3-113">Progress is calculated for a top-level item, such as a parent folder.</span></span> <span data-ttu-id="9abc3-114">进度对象应[IMAPIProgress::Progress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数中使用的值，其中分别指示当前项目和操作中的项 — 递增进度此操作的指示器。</span><span class="sxs-lookup"><span data-stu-id="9abc3-114">The progress object should use the values in the [IMAPIProgress::Progress](imapiprogress-progress.md) method's  _ulCount_ and  _ulTotal_ parameters — which indicate the current item and the total items in the operation, respectively — to increment the progress indicator for the operation.</span></span> 
    
 <span data-ttu-id="9abc3-115">_lppProgress_</span><span class="sxs-lookup"><span data-stu-id="9abc3-115">_lppProgress_</span></span>
  
> <span data-ttu-id="9abc3-116">[输出]指向进度对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9abc3-116">[out] A pointer to a pointer to the progress object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9abc3-117">返回值</span><span class="sxs-lookup"><span data-stu-id="9abc3-117">Return value</span></span>

<span data-ttu-id="9abc3-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="9abc3-118">S_OK</span></span> 
  
> <span data-ttu-id="9abc3-119">已成功检索进度对象。</span><span class="sxs-lookup"><span data-stu-id="9abc3-119">The progress object was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9abc3-120">说明</span><span class="sxs-lookup"><span data-stu-id="9abc3-120">Remarks</span></span>

<span data-ttu-id="9abc3-121">对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::DoProgressDialog**方法。</span><span class="sxs-lookup"><span data-stu-id="9abc3-121">The **IMAPISupport::DoProgressDialog** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="9abc3-122">这些提供程序调用**DoProgressDialog**来访问 MAPI 实现的[IMAPIProgress](imapiprogressiunknown.md)接口，计算进度信息并显示一个标准的对话框。</span><span class="sxs-lookup"><span data-stu-id="9abc3-122">These providers call **DoProgressDialog** to access the MAPI implementation of the [IMAPIProgress](imapiprogressiunknown.md) interface, which calculates the progress information and displays a standard dialog box.</span></span> 
  
<span data-ttu-id="9abc3-123">有关如何使用进度对象和**IMAPIProgress**接口的信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="9abc3-123">For information about how to use a progress object and the **IMAPIProgress** interface, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9abc3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9abc3-124">See also</span></span>



[<span data-ttu-id="9abc3-125">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9abc3-125">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="9abc3-126">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="9abc3-126">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="9abc3-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9abc3-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="9abc3-128">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="9abc3-128">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)

