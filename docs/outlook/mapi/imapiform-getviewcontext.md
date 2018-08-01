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
ms.openlocfilehash: 2c463252aa029ac4c7cb2fac6e962a5d8af31b97
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775371"
---
# <a name="imapiformgetviewcontext"></a><span data-ttu-id="e0302-103">IMAPIForm::GetViewContext</span><span class="sxs-lookup"><span data-stu-id="e0302-103">IMAPIForm::GetViewContext</span></span>

  
  
<span data-ttu-id="e0302-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0302-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0302-105">返回表单的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e0302-105">Returns the current view context for the form.</span></span> 
  
```cpp
HRESULT GetViewContext(
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a><span data-ttu-id="e0302-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0302-106">Parameters</span></span>

 <span data-ttu-id="e0302-107">_ppViewContext_</span><span class="sxs-lookup"><span data-stu-id="e0302-107">_ppViewContext_</span></span>
  
> <span data-ttu-id="e0302-108">[输出]指向到窗体的视图上下文的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e0302-108">[out] A pointer to a pointer to the form's view context.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e0302-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e0302-109">Return value</span></span>

<span data-ttu-id="e0302-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0302-110">S_OK</span></span> 
  
> <span data-ttu-id="e0302-111">已成功返回窗体的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e0302-111">The form's current view context was successfully returned.</span></span> 
    
<span data-ttu-id="e0302-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e0302-112">S_FALSE</span></span> 
  
> <span data-ttu-id="e0302-113">没有窗体视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e0302-113">There is no view context for the form.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e0302-114">说明</span><span class="sxs-lookup"><span data-stu-id="e0302-114">Remarks</span></span>

<span data-ttu-id="e0302-115">表单查看器调用**GetViewContext**以获取视图上下文中向[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)以前呼叫建立的指针。</span><span class="sxs-lookup"><span data-stu-id="e0302-115">Form viewers call **GetViewContext** to obtain a pointer to the view context established in a previous call to [IMAPIForm::SetViewContext](imapiform-setviewcontext.md).</span></span> <span data-ttu-id="e0302-116">如果对**SetViewContext**不进行了任何以前的呼叫， **GetViewContext**将_ppViewContext_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e0302-116">If no prior call has been made to **SetViewContext**, **GetViewContext** sets  _ppViewContext_ to NULL.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e0302-117">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e0302-117">Notes to implementers</span></span>

<span data-ttu-id="e0302-118">将窗体的视图上下文指针复制到传入呼叫的窗体查看_ppViewContext_参数中的指针。</span><span class="sxs-lookup"><span data-stu-id="e0302-118">Copy your form's view context pointer into the pointer passed in by the calling form viewer in the  _ppViewContext_ parameter.</span></span> <span data-ttu-id="e0302-119">如果表单没有了视图上下文，设置为 NULL _ppViewContext_ 。</span><span class="sxs-lookup"><span data-stu-id="e0302-119">If the form does not have a view context, set  _ppViewContext_ to NULL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e0302-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e0302-120">MFCMAPI reference</span></span>

<span data-ttu-id="e0302-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e0302-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e0302-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="e0302-122">**File**</span></span>|<span data-ttu-id="e0302-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="e0302-123">**Function**</span></span>|<span data-ttu-id="e0302-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e0302-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0302-125">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="e0302-125">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="e0302-126">OpenMessageNonModal</span><span class="sxs-lookup"><span data-stu-id="e0302-126">OpenMessageNonModal</span></span>  <br/> |<span data-ttu-id="e0302-127">MFCMAPI 使用**IMAPIForm::GetViewContext**方法来检查窗体是否有了视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e0302-127">MFCMAPI uses the **IMAPIForm::GetViewContext** method to check whether a form has a view context.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e0302-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0302-128">See also</span></span>



[<span data-ttu-id="e0302-129">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e0302-129">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)
  
[<span data-ttu-id="e0302-130">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e0302-130">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="e0302-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e0302-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

