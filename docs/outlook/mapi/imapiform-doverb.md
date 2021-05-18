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
ms.openlocfilehash: 60a8c89afe0d70a1737c6ce694c66359fd6aae4f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329454"
---
# <a name="imapiformdoverb"></a><span data-ttu-id="487b1-103">IMAPIForm::DoVerb</span><span class="sxs-lookup"><span data-stu-id="487b1-103">IMAPIForm::DoVerb</span></span>

  
  
<span data-ttu-id="487b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="487b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="487b1-105">请求表单执行与特定动词关联的任何任务。</span><span class="sxs-lookup"><span data-stu-id="487b1-105">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>
  
```cpp
HRESULT DoVerb(
  LONG iVerb,
  LPMAPIVIEWCONTEXT lpViewContext,
  ULONG_PTR hwndParent,
  LPCRECT lprcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="487b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="487b1-106">Parameters</span></span>

 <span data-ttu-id="487b1-107">_iVerb_</span><span class="sxs-lookup"><span data-stu-id="487b1-107">_iVerb_</span></span>
  
> <span data-ttu-id="487b1-108">[in]与窗体动作之一相关联的数字。</span><span class="sxs-lookup"><span data-stu-id="487b1-108">[in] The number associated with one of the form's verbs.</span></span>
    
 <span data-ttu-id="487b1-109">_lpViewContext_</span><span class="sxs-lookup"><span data-stu-id="487b1-109">_lpViewContext_</span></span>
  
> <span data-ttu-id="487b1-110">[in]指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="487b1-110">[in] A pointer to a view context object.</span></span> <span data-ttu-id="487b1-111">_lpViewContext_ 参数可以是 **null**。</span><span class="sxs-lookup"><span data-stu-id="487b1-111">The  _lpViewContext_ parameter can be **null**.</span></span>
    
 <span data-ttu-id="487b1-112">_hwndParent_</span><span class="sxs-lookup"><span data-stu-id="487b1-112">_hwndParent_</span></span>
  
> <span data-ttu-id="487b1-113">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="487b1-113">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="487b1-114">如果对话框或窗口不是模式对话框或窗口，_则 hwndParent_ 参数应为 null。</span><span class="sxs-lookup"><span data-stu-id="487b1-114">The  _hwndParent_ parameter should be **null** if the dialog box or window is not modal.</span></span> 
    
 <span data-ttu-id="487b1-115">_lprcPosRect_</span><span class="sxs-lookup"><span data-stu-id="487b1-115">_lprcPosRect_</span></span>
  
> <span data-ttu-id="487b1-116">[in]指向包含窗体窗口大小和位置的 Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="487b1-116">[in] A pointer to a Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) structure that contains the size and position of the form's window.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="487b1-117">返回值</span><span class="sxs-lookup"><span data-stu-id="487b1-117">Return value</span></span>

<span data-ttu-id="487b1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="487b1-118">S_OK</span></span> 
  
> <span data-ttu-id="487b1-119">动词命令已成功调用。</span><span class="sxs-lookup"><span data-stu-id="487b1-119">The verb was successfully invoked.</span></span>
    
<span data-ttu-id="487b1-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span><span class="sxs-lookup"><span data-stu-id="487b1-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span></span> 
  
> <span data-ttu-id="487b1-121">_iVerb_ 参数表示的谓词有效，但表单无法执行当前与之关联的操作。</span><span class="sxs-lookup"><span data-stu-id="487b1-121">The verb represented by the  _iVerb_ parameter is valid, but the form cannot perform the operations currently associated with it.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="487b1-122">备注</span><span class="sxs-lookup"><span data-stu-id="487b1-122">Remarks</span></span>

<span data-ttu-id="487b1-123">表单查看者调用 **IMAPIForm：:D oVerb** 方法，以请求表单执行与表单支持的每个动作关联的任务。</span><span class="sxs-lookup"><span data-stu-id="487b1-123">Form viewers call the **IMAPIForm::DoVerb** method to request that the form perform the tasks that it associates with each verb that the form supports.</span></span> 
  
<span data-ttu-id="487b1-124">每个受支持的动词都由一个数值标识，在 **iVerb** 参数中传递给 _DoVerb。_</span><span class="sxs-lookup"><span data-stu-id="487b1-124">Each of the supported verbs is identified by a numeric value, passed to **DoVerb** in the  _iVerb_ parameter.</span></span> <span data-ttu-id="487b1-125">**DoVerb 的典型** 实现包含 **一个 switch** 语句，该语句测试对表单 _的 iVerb_ 参数有效的值。</span><span class="sxs-lookup"><span data-stu-id="487b1-125">Typical implementations of **DoVerb** contain a **switch** statement that tests the values that are valid for the  _iVerb_ parameter for the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="487b1-126">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="487b1-126">Notes to implementers</span></span>

<span data-ttu-id="487b1-127">如果表单查看器在  _lpViewContext_ 参数中指定视图上下文，请在你的 **DoVerb** 实现中使用它，而不是在之前对 [IMAPIForm：：SetViewContext](imapiform-setviewcontext.md) 方法的调用中传递的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="487b1-127">If the form viewer specifies a view context in the  _lpViewContext_ parameter, use it in your **DoVerb** implementation instead of the view context passed in an earlier call to the [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method.</span></span> <span data-ttu-id="487b1-128">对内部数据结构进行所需的任何更改，不要保存视图上下文。</span><span class="sxs-lookup"><span data-stu-id="487b1-128">Make whatever changes are necessary to your internal data structures and do not save the view context.</span></span> 
  
<span data-ttu-id="487b1-129">在 **DoVerb** 实现中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="487b1-129">Perform the following tasks in your **DoVerb** implementation:</span></span> 
  
- <span data-ttu-id="487b1-130">执行与  _iVerb_ 参数关联的特定动作所需的任何代码。</span><span class="sxs-lookup"><span data-stu-id="487b1-130">Execute whatever code is necessary for the particular verb that is associated with the  _iVerb_ parameter.</span></span> 
    
- <span data-ttu-id="487b1-131">如有必要，还原原始视图上下文。</span><span class="sxs-lookup"><span data-stu-id="487b1-131">If necessary, restore the original view context.</span></span>
    
- <span data-ttu-id="487b1-132">如果传入了未知动词数字，则返回MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="487b1-132">If an unknown verb number was passed in, return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="487b1-133">否则，根据所执行的任何动词的成功或失败返回结果。</span><span class="sxs-lookup"><span data-stu-id="487b1-133">Otherwise, return a result based on the success or failure of whatever verb was executed.</span></span>
    
- <span data-ttu-id="487b1-134">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="487b1-134">Close the form.</span></span> <span data-ttu-id="487b1-135">您始终负责在 **DoVerb** 调用完成后关闭表单。</span><span class="sxs-lookup"><span data-stu-id="487b1-135">It is always your responsibility to close the form after a **DoVerb** call completes.</span></span> 
    
<span data-ttu-id="487b1-136">某些动作（如 Print）对于 **DoVerb** 调用应该具有模式，也就是说，指示的操作必须在 **DoVerb** 调用返回之前完成。</span><span class="sxs-lookup"><span data-stu-id="487b1-136">Some verbs, such as Print, should be modal with respect to the **DoVerb** call — that is, the indicated operation must be finished before the **DoVerb** call returns.</span></span> 
  
<span data-ttu-id="487b1-137">若要获取窗体窗口使用的 **RECT** 结构，请调用 [GetWindowRect](https://msdn.microsoft.com/library/ms633519) 函数。</span><span class="sxs-lookup"><span data-stu-id="487b1-137">To obtain the **RECT** structure used by a form's window, call the [GetWindowRect](https://msdn.microsoft.com/library/ms633519) function.</span></span> 
  
<span data-ttu-id="487b1-138">不要将句柄保存在  _hwndParent_ 参数中，因为尽管它通常保持有效直到 **DoVerb** 完成，但它可以在调用返回后立即销毁。</span><span class="sxs-lookup"><span data-stu-id="487b1-138">Do not save the handle in the  _hwndParent_ parameter because, although it usually remains valid until the completion of **DoVerb**, it can be destroyed immediately upon the call's return.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="487b1-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="487b1-139">Notes to callers</span></span>

<span data-ttu-id="487b1-140">您可以通过将  _lpViewContext_ 指向从 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法返回 VCSTATUS_MODAL 标志的视图上下文实现，使非模式动词用作模式动词。</span><span class="sxs-lookup"><span data-stu-id="487b1-140">You can make non-modal verbs act as modal verbs by pointing  _lpViewContext_ to a view context implementation that returns the VCSTATUS_MODAL flag from its [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
  
<span data-ttu-id="487b1-141">有关 MAPI 中的动词功能详细信息，请参阅 [Form Verbs](form-verbs.md)。</span><span class="sxs-lookup"><span data-stu-id="487b1-141">For more information about verbs in MAPI, see [Form Verbs](form-verbs.md).</span></span> <span data-ttu-id="487b1-142">有关在 OLE 中如何处理动作的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="487b1-142">For more information about how verbs are handled in OLE, see [OLE and Data Transfer](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="487b1-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="487b1-143">MFCMAPI reference</span></span>

<span data-ttu-id="487b1-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="487b1-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="487b1-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="487b1-145">**File**</span></span>|<span data-ttu-id="487b1-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="487b1-146">**Function**</span></span>|<span data-ttu-id="487b1-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="487b1-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="487b1-148">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="487b1-148">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="487b1-149">CMyMAPIFormViewer：：CallDoVerb</span><span class="sxs-lookup"><span data-stu-id="487b1-149">CMyMAPIFormViewer::CallDoVerb</span></span>  <br/> |<span data-ttu-id="487b1-150">MFCMAPI 使用 **IMAPIForm：:D oVerb** 方法调用表单上的动词。</span><span class="sxs-lookup"><span data-stu-id="487b1-150">MFCMAPI uses the **IMAPIForm::DoVerb** method to invoke a verb on a form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="487b1-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="487b1-151">See also</span></span>



[<span data-ttu-id="487b1-152">IMAPIForm::SetViewContext</span><span class="sxs-lookup"><span data-stu-id="487b1-152">IMAPIForm::SetViewContext</span></span>](imapiform-setviewcontext.md)
  
[<span data-ttu-id="487b1-153">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="487b1-153">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
  
[<span data-ttu-id="487b1-154">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="487b1-154">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="487b1-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="487b1-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="487b1-156">窗体动词</span><span class="sxs-lookup"><span data-stu-id="487b1-156">Form Verbs</span></span>](form-verbs.md)

