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
ms.openlocfilehash: 9f09f29d67bff6588c826b92d93aead491510cef
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574816"
---
# <a name="imapiformgetviewcontext"></a><span data-ttu-id="fd679-103">IMAPIForm::GetViewContext</span><span class="sxs-lookup"><span data-stu-id="fd679-103">IMAPIForm::GetViewContext</span></span>

  
  
<span data-ttu-id="fd679-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd679-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd679-105">返回表单的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="fd679-105">Returns the current view context for the form.</span></span> 
  
```cpp
HRESULT GetViewContext(
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a><span data-ttu-id="fd679-106">参数</span><span class="sxs-lookup"><span data-stu-id="fd679-106">Parameters</span></span>

 <span data-ttu-id="fd679-107">_ppViewContext_</span><span class="sxs-lookup"><span data-stu-id="fd679-107">_ppViewContext_</span></span>
  
> <span data-ttu-id="fd679-108">[输出]指向到窗体的视图上下文的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fd679-108">[out] A pointer to a pointer to the form's view context.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fd679-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fd679-109">Return value</span></span>

<span data-ttu-id="fd679-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd679-110">S_OK</span></span> 
  
> <span data-ttu-id="fd679-111">已成功返回窗体的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="fd679-111">The form's current view context was successfully returned.</span></span> 
    
<span data-ttu-id="fd679-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fd679-112">S_FALSE</span></span> 
  
> <span data-ttu-id="fd679-113">没有窗体视图上下文。</span><span class="sxs-lookup"><span data-stu-id="fd679-113">There is no view context for the form.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fd679-114">注解</span><span class="sxs-lookup"><span data-stu-id="fd679-114">Remarks</span></span>

<span data-ttu-id="fd679-115">表单查看器调用**GetViewContext**以获取视图上下文中向[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)以前呼叫建立的指针。</span><span class="sxs-lookup"><span data-stu-id="fd679-115">Form viewers call **GetViewContext** to obtain a pointer to the view context established in a previous call to [IMAPIForm::SetViewContext](imapiform-setviewcontext.md).</span></span> <span data-ttu-id="fd679-116">如果对**SetViewContext**不进行了任何以前的呼叫， **GetViewContext**将_ppViewContext_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fd679-116">If no prior call has been made to **SetViewContext**, **GetViewContext** sets  _ppViewContext_ to NULL.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="fd679-117">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="fd679-117">Notes to implementers</span></span>

<span data-ttu-id="fd679-118">将窗体的视图上下文指针复制到传入呼叫的窗体查看_ppViewContext_参数中的指针。</span><span class="sxs-lookup"><span data-stu-id="fd679-118">Copy your form's view context pointer into the pointer passed in by the calling form viewer in the  _ppViewContext_ parameter.</span></span> <span data-ttu-id="fd679-119">如果表单没有了视图上下文，设置为 NULL _ppViewContext_ 。</span><span class="sxs-lookup"><span data-stu-id="fd679-119">If the form does not have a view context, set  _ppViewContext_ to NULL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fd679-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="fd679-120">MFCMAPI reference</span></span>

<span data-ttu-id="fd679-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fd679-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fd679-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="fd679-122">**File**</span></span>|<span data-ttu-id="fd679-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="fd679-123">**Function**</span></span>|<span data-ttu-id="fd679-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="fd679-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd679-125">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="fd679-125">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="fd679-126">OpenMessageNonModal</span><span class="sxs-lookup"><span data-stu-id="fd679-126">OpenMessageNonModal</span></span>  <br/> |<span data-ttu-id="fd679-127">MFCMAPI 使用**IMAPIForm::GetViewContext**方法来检查窗体是否有了视图上下文。</span><span class="sxs-lookup"><span data-stu-id="fd679-127">MFCMAPI uses the **IMAPIForm::GetViewContext** method to check whether a form has a view context.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fd679-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd679-128">See also</span></span>



[<span data-ttu-id="fd679-129">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fd679-129">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
  
[<span data-ttu-id="fd679-130">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fd679-130">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="fd679-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fd679-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

