---
title: IMAPIFormGetViewContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.GetViewContext
api_type:
- COM
ms.assetid: c6938986-a9f9-4ef4-9655-ded55b7357db
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f0b217372f6b4848f83c993846cd08a81c7098e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430901"
---
# <a name="imapiformgetviewcontext"></a><span data-ttu-id="f70ea-103">IMAPIForm::GetViewContext</span><span class="sxs-lookup"><span data-stu-id="f70ea-103">IMAPIForm::GetViewContext</span></span>

  
  
<span data-ttu-id="f70ea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f70ea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f70ea-105">返回窗体的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f70ea-105">Returns the current view context for the form.</span></span> 
  
```cpp
HRESULT GetViewContext(
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a><span data-ttu-id="f70ea-106">参数</span><span class="sxs-lookup"><span data-stu-id="f70ea-106">Parameters</span></span>

 <span data-ttu-id="f70ea-107">_ppViewContext_</span><span class="sxs-lookup"><span data-stu-id="f70ea-107">_ppViewContext_</span></span>
  
> <span data-ttu-id="f70ea-108">排除指向表单的视图上下文的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f70ea-108">[out] A pointer to a pointer to the form's view context.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f70ea-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f70ea-109">Return value</span></span>

<span data-ttu-id="f70ea-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f70ea-110">S_OK</span></span> 
  
> <span data-ttu-id="f70ea-111">已成功返回表单的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f70ea-111">The form's current view context was successfully returned.</span></span> 
    
<span data-ttu-id="f70ea-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f70ea-112">S_FALSE</span></span> 
  
> <span data-ttu-id="f70ea-113">没有表单的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f70ea-113">There is no view context for the form.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f70ea-114">说明</span><span class="sxs-lookup"><span data-stu-id="f70ea-114">Remarks</span></span>

<span data-ttu-id="f70ea-115">表单查看者调用**GetViewContext**以获取指向在之前调用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)时建立的视图上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="f70ea-115">Form viewers call **GetViewContext** to obtain a pointer to the view context established in a previous call to [IMAPIForm::SetViewContext](imapiform-setviewcontext.md).</span></span> <span data-ttu-id="f70ea-116">如果之前未对**SetViewContext**进行任何调用, 则**GetViewContext**会将_ppViewContext_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f70ea-116">If no prior call has been made to **SetViewContext**, **GetViewContext** sets  _ppViewContext_ to NULL.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f70ea-117">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="f70ea-117">Notes to implementers</span></span>

<span data-ttu-id="f70ea-118">将表单的视图上下文指针复制到由_ppViewContext_参数中的调用表单查看器传入的指针中。</span><span class="sxs-lookup"><span data-stu-id="f70ea-118">Copy your form's view context pointer into the pointer passed in by the calling form viewer in the  _ppViewContext_ parameter.</span></span> <span data-ttu-id="f70ea-119">如果窗体没有视图上下文, 则将_ppViewContext_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f70ea-119">If the form does not have a view context, set  _ppViewContext_ to NULL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f70ea-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f70ea-120">MFCMAPI reference</span></span>

<span data-ttu-id="f70ea-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f70ea-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f70ea-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="f70ea-122">**File**</span></span>|<span data-ttu-id="f70ea-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="f70ea-123">**Function**</span></span>|<span data-ttu-id="f70ea-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="f70ea-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f70ea-125">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="f70ea-125">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="f70ea-126">OpenMessageNonModal</span><span class="sxs-lookup"><span data-stu-id="f70ea-126">OpenMessageNonModal</span></span>  <br/> |<span data-ttu-id="f70ea-127">MFCMAPI 使用**IMAPIForm:: GetViewContext**方法检查窗体中是否有视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f70ea-127">MFCMAPI uses the **IMAPIForm::GetViewContext** method to check whether a form has a view context.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f70ea-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f70ea-128">See also</span></span>



[<span data-ttu-id="f70ea-129">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f70ea-129">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
  
[<span data-ttu-id="f70ea-130">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f70ea-130">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="f70ea-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f70ea-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

