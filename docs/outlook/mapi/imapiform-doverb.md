---
title: IMAPIFormDoVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.DoVerb
api_type:
- COM
ms.assetid: 8b582571-b448-4476-91d9-4cc94dbec710
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fe6270d82d227f52dfd5dfa5454c73e815ad9f42
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573815"
---
# <a name="imapiformdoverb"></a><span data-ttu-id="b8e51-103">IMAPIForm::DoVerb</span><span class="sxs-lookup"><span data-stu-id="b8e51-103">IMAPIForm::DoVerb</span></span>

  
  
<span data-ttu-id="b8e51-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b8e51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b8e51-105">请求窗体执行任何任务它将与特定动词。</span><span class="sxs-lookup"><span data-stu-id="b8e51-105">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>
  
```cpp
HRESULT DoVerb(
  LONG iVerb,
  LPMAPIVIEWCONTEXT lpViewContext,
  ULONG_PTR hwndParent,
  LPCRECT lprcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="b8e51-106">参数</span><span class="sxs-lookup"><span data-stu-id="b8e51-106">Parameters</span></span>

 <span data-ttu-id="b8e51-107">_iVerb_</span><span class="sxs-lookup"><span data-stu-id="b8e51-107">_iVerb_</span></span>
  
> <span data-ttu-id="b8e51-108">[in]使用一个窗体的动作相关联的编号。</span><span class="sxs-lookup"><span data-stu-id="b8e51-108">[in] The number associated with one of the form's verbs.</span></span>
    
 <span data-ttu-id="b8e51-109">_lpViewContext_</span><span class="sxs-lookup"><span data-stu-id="b8e51-109">_lpViewContext_</span></span>
  
> <span data-ttu-id="b8e51-110">[in]指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b8e51-110">[in] A pointer to a view context object.</span></span> <span data-ttu-id="b8e51-111">_LpViewContext_参数可以为**null**。</span><span class="sxs-lookup"><span data-stu-id="b8e51-111">The  _lpViewContext_ parameter can be **null**.</span></span>
    
 <span data-ttu-id="b8e51-112">_hwndParent_</span><span class="sxs-lookup"><span data-stu-id="b8e51-112">_hwndParent_</span></span>
  
> <span data-ttu-id="b8e51-113">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="b8e51-113">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="b8e51-114">如果对话框或窗口不是模式， _hwndParent_参数应为**null** 。</span><span class="sxs-lookup"><span data-stu-id="b8e51-114">The  _hwndParent_ parameter should be **null** if the dialog box or window is not modal.</span></span> 
    
 <span data-ttu-id="b8e51-115">_lprcPosRect_</span><span class="sxs-lookup"><span data-stu-id="b8e51-115">_lprcPosRect_</span></span>
  
> <span data-ttu-id="b8e51-116">[in]指向 Win32[矩形](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx)结构，其中包含的大小和窗体的窗口的位置。</span><span class="sxs-lookup"><span data-stu-id="b8e51-116">[in] A pointer to a Win32 [RECT](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx) structure that contains the size and position of the form's window.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b8e51-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b8e51-117">Return value</span></span>

<span data-ttu-id="b8e51-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8e51-118">S_OK</span></span> 
  
> <span data-ttu-id="b8e51-119">成功调用动词。</span><span class="sxs-lookup"><span data-stu-id="b8e51-119">The verb was successfully invoked.</span></span>
    
<span data-ttu-id="b8e51-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span><span class="sxs-lookup"><span data-stu-id="b8e51-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span></span> 
  
> <span data-ttu-id="b8e51-121">由_iVerb_参数表示的动作有效，但表单无法执行与其当前关联的操作。</span><span class="sxs-lookup"><span data-stu-id="b8e51-121">The verb represented by the  _iVerb_ parameter is valid, but the form cannot perform the operations currently associated with it.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b8e51-122">注解</span><span class="sxs-lookup"><span data-stu-id="b8e51-122">Remarks</span></span>

<span data-ttu-id="b8e51-123">表单查看器调用**IMAPIForm::DoVerb**方法以请求窗体执行它将与该窗体支持每个动作相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="b8e51-123">Form viewers call the **IMAPIForm::DoVerb** method to request that the form perform the tasks that it associates with each verb that the form supports.</span></span> 
  
<span data-ttu-id="b8e51-124">每个受支持的动作由传递给**DoVerb** _iVerb_参数中的数值标识。</span><span class="sxs-lookup"><span data-stu-id="b8e51-124">Each of the supported verbs is identified by a numeric value, passed to **DoVerb** in the  _iVerb_ parameter.</span></span> <span data-ttu-id="b8e51-125">**DoVerb**的典型实现包含**switch**语句的测试可用于窗体的_iVerb_参数的值。</span><span class="sxs-lookup"><span data-stu-id="b8e51-125">Typical implementations of **DoVerb** contain a **switch** statement that tests the values that are valid for the  _iVerb_ parameter for the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b8e51-126">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="b8e51-126">Notes to implementers</span></span>

<span data-ttu-id="b8e51-127">如果表单查看器_lpViewContext_参数中指定了视图上下文，则**DoVerb**实现而不是以前[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法调用中传递的视图上下文中使用它。</span><span class="sxs-lookup"><span data-stu-id="b8e51-127">If the form viewer specifies a view context in the  _lpViewContext_ parameter, use it in your **DoVerb** implementation instead of the view context passed in an earlier call to the [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method.</span></span> <span data-ttu-id="b8e51-128">进行任何更改是向内部数据结构所必需的且不保存视图上下文。</span><span class="sxs-lookup"><span data-stu-id="b8e51-128">Make whatever changes are necessary to your internal data structures and do not save the view context.</span></span> 
  
<span data-ttu-id="b8e51-129">**DoVerb**实现中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b8e51-129">Perform the following tasks in your **DoVerb** implementation:</span></span> 
  
- <span data-ttu-id="b8e51-130">执行任何代码是必要的特定谓词的与_iVerb_参数相关联。</span><span class="sxs-lookup"><span data-stu-id="b8e51-130">Execute whatever code is necessary for the particular verb that is associated with the  _iVerb_ parameter.</span></span> 
    
- <span data-ttu-id="b8e51-131">如有必要，还原原始视图上下文。</span><span class="sxs-lookup"><span data-stu-id="b8e51-131">If necessary, restore the original view context.</span></span>
    
- <span data-ttu-id="b8e51-132">如果中传递了未知的动词数，返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="b8e51-132">If an unknown verb number was passed in, return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="b8e51-133">否则，返回基于是成功还是失败的执行任何操作的结果。</span><span class="sxs-lookup"><span data-stu-id="b8e51-133">Otherwise, return a result based on the success or failure of whatever verb was executed.</span></span>
    
- <span data-ttu-id="b8e51-134">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="b8e51-134">Close the form.</span></span> <span data-ttu-id="b8e51-135">它始终是您有责任**DoVerb**调用完成后关闭表单。</span><span class="sxs-lookup"><span data-stu-id="b8e51-135">It is always your responsibility to close the form after a **DoVerb** call completes.</span></span> 
    
<span data-ttu-id="b8e51-136">某些谓词，如打印，应为模式相对于**DoVerb**呼叫 — 即，指示的操作必须**DoVerb**调用返回之前完成。</span><span class="sxs-lookup"><span data-stu-id="b8e51-136">Some verbs, such as Print, should be modal with respect to the **DoVerb** call — that is, the indicated operation must be finished before the **DoVerb** call returns.</span></span> 
  
<span data-ttu-id="b8e51-137">若要获取使用窗体的窗口的**矩形**结构，请调用[GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="b8e51-137">To obtain the **RECT** structure used by a form's window, call the [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519) function.</span></span> 
  
<span data-ttu-id="b8e51-138">因为，但它通常保持有效**DoVerb**完成之后，它可以销毁立即的调用返回时，不要_hwndParent_参数中保存句柄。</span><span class="sxs-lookup"><span data-stu-id="b8e51-138">Do not save the handle in the  _hwndParent_ parameter because, although it usually remains valid until the completion of **DoVerb**, it can be destroyed immediately upon the call's return.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="b8e51-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b8e51-139">Notes to callers</span></span>

<span data-ttu-id="b8e51-140">您可以通过从其[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)方法返回 VCSTATUS_MODAL 标志视图上下文实现指向_lpViewContext_用作模式谓词的非模式动词。</span><span class="sxs-lookup"><span data-stu-id="b8e51-140">You can make non-modal verbs act as modal verbs by pointing  _lpViewContext_ to a view context implementation that returns the VCSTATUS_MODAL flag from its [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
  
<span data-ttu-id="b8e51-141">有关谓词 MAPI 中的详细信息，请参阅[窗体动词](form-verbs.md)。</span><span class="sxs-lookup"><span data-stu-id="b8e51-141">For more information about verbs in MAPI, see [Form Verbs](form-verbs.md).</span></span> <span data-ttu-id="b8e51-142">有关在 OLE 动作的处理方式的详细信息，请参阅[OLE 和数据传输](http://msdn.microsoft.com/en-us/library/ms693425%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b8e51-142">For more information about how verbs are handled in OLE, see [OLE and Data Transfer](http://msdn.microsoft.com/en-us/library/ms693425%28VS.85%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b8e51-143">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b8e51-143">MFCMAPI reference</span></span>

<span data-ttu-id="b8e51-144">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b8e51-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b8e51-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="b8e51-145">**File**</span></span>|<span data-ttu-id="b8e51-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="b8e51-146">**Function**</span></span>|<span data-ttu-id="b8e51-147">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b8e51-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8e51-148">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="b8e51-148">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="b8e51-149">CMyMAPIFormViewer::CallDoVerb</span><span class="sxs-lookup"><span data-stu-id="b8e51-149">CMyMAPIFormViewer::CallDoVerb</span></span>  <br/> |<span data-ttu-id="b8e51-150">MFCMAPI 使用**IMAPIForm::DoVerb**方法调用窗体上的动词。</span><span class="sxs-lookup"><span data-stu-id="b8e51-150">MFCMAPI uses the **IMAPIForm::DoVerb** method to invoke a verb on a form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b8e51-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e51-151">See also</span></span>



[<span data-ttu-id="b8e51-152">IMAPIForm::SetViewContext</span><span class="sxs-lookup"><span data-stu-id="b8e51-152">IMAPIForm::SetViewContext</span></span>](imapiform-setviewcontext.md)
  
[<span data-ttu-id="b8e51-153">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="b8e51-153">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
  
[<span data-ttu-id="b8e51-154">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b8e51-154">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="b8e51-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b8e51-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="b8e51-156">表单谓词</span><span class="sxs-lookup"><span data-stu-id="b8e51-156">Form Verbs</span></span>](form-verbs.md)

