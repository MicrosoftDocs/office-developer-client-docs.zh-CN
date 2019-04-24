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
# <a name="imapiformdoverb"></a><span data-ttu-id="e6041-103">IMAPIForm::DoVerb</span><span class="sxs-lookup"><span data-stu-id="e6041-103">IMAPIForm::DoVerb</span></span>

  
  
<span data-ttu-id="e6041-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6041-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6041-105">请求表单执行与特定谓词相关联的任何任务。</span><span class="sxs-lookup"><span data-stu-id="e6041-105">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>
  
```cpp
HRESULT DoVerb(
  LONG iVerb,
  LPMAPIVIEWCONTEXT lpViewContext,
  ULONG_PTR hwndParent,
  LPCRECT lprcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="e6041-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6041-106">Parameters</span></span>

 <span data-ttu-id="e6041-107">_iVerb_</span><span class="sxs-lookup"><span data-stu-id="e6041-107">_iVerb_</span></span>
  
> <span data-ttu-id="e6041-108">实时与窗体的一个谓词相关联的数字。</span><span class="sxs-lookup"><span data-stu-id="e6041-108">[in] The number associated with one of the form's verbs.</span></span>
    
 <span data-ttu-id="e6041-109">_lpViewContext_</span><span class="sxs-lookup"><span data-stu-id="e6041-109">_lpViewContext_</span></span>
  
> <span data-ttu-id="e6041-110">实时指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e6041-110">[in] A pointer to a view context object.</span></span> <span data-ttu-id="e6041-111">_lpViewContext_参数可以为**null**。</span><span class="sxs-lookup"><span data-stu-id="e6041-111">The  _lpViewContext_ parameter can be **null**.</span></span>
    
 <span data-ttu-id="e6041-112">_hwndParent_</span><span class="sxs-lookup"><span data-stu-id="e6041-112">_hwndParent_</span></span>
  
> <span data-ttu-id="e6041-113">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e6041-113">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="e6041-114">如果对话框或窗口不模式, 则_hwndParent_参数应为**null** 。</span><span class="sxs-lookup"><span data-stu-id="e6041-114">The  _hwndParent_ parameter should be **null** if the dialog box or window is not modal.</span></span> 
    
 <span data-ttu-id="e6041-115">_lprcPosRect_</span><span class="sxs-lookup"><span data-stu-id="e6041-115">_lprcPosRect_</span></span>
  
> <span data-ttu-id="e6041-116">实时指向 Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx)结构的指针, 该结构包含窗体的窗口的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="e6041-116">[in] A pointer to a Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) structure that contains the size and position of the form's window.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e6041-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e6041-117">Return value</span></span>

<span data-ttu-id="e6041-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6041-118">S_OK</span></span> 
  
> <span data-ttu-id="e6041-119">已成功调用谓词。</span><span class="sxs-lookup"><span data-stu-id="e6041-119">The verb was successfully invoked.</span></span>
    
<span data-ttu-id="e6041-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span><span class="sxs-lookup"><span data-stu-id="e6041-120">OLEOBJ_S_CANNOT_DOVERB_NOW</span></span> 
  
> <span data-ttu-id="e6041-121">由_iVerb_参数表示的谓词是有效的, 但该窗体无法执行当前与之关联的操作。</span><span class="sxs-lookup"><span data-stu-id="e6041-121">The verb represented by the  _iVerb_ parameter is valid, but the form cannot perform the operations currently associated with it.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e6041-122">注解</span><span class="sxs-lookup"><span data-stu-id="e6041-122">Remarks</span></span>

<span data-ttu-id="e6041-123">表单查看器调用**IMAPIForm::D overb**方法, 以请求表单执行与表单支持的每个谓词相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="e6041-123">Form viewers call the **IMAPIForm::DoVerb** method to request that the form perform the tasks that it associates with each verb that the form supports.</span></span> 
  
<span data-ttu-id="e6041-124">每个受支持的谓词都通过一个数值标识, 并传递给_iVerb_参数中的**DoVerb** 。</span><span class="sxs-lookup"><span data-stu-id="e6041-124">Each of the supported verbs is identified by a numeric value, passed to **DoVerb** in the  _iVerb_ parameter.</span></span> <span data-ttu-id="e6041-125">**DoVerb**的典型实现包含一个**switch**语句, 用于测试对窗体的_iVerb_参数有效的值。</span><span class="sxs-lookup"><span data-stu-id="e6041-125">Typical implementations of **DoVerb** contain a **switch** statement that tests the values that are valid for the  _iVerb_ parameter for the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e6041-126">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="e6041-126">Notes to implementers</span></span>

<span data-ttu-id="e6041-127">如果表单查看器在_lpViewContext_参数中指定了视图上下文, 请在**DoVerb**实现中使用它, 而不是在之前调用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法时传递的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e6041-127">If the form viewer specifies a view context in the  _lpViewContext_ parameter, use it in your **DoVerb** implementation instead of the view context passed in an earlier call to the [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method.</span></span> <span data-ttu-id="e6041-128">对内部数据结构进行任何所需的更改, 并且不保存视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e6041-128">Make whatever changes are necessary to your internal data structures and do not save the view context.</span></span> 
  
<span data-ttu-id="e6041-129">在您的**DoVerb**实现中执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="e6041-129">Perform the following tasks in your **DoVerb** implementation:</span></span> 
  
- <span data-ttu-id="e6041-130">执行与_iVerb_参数关联的特定谓词所需的任何代码。</span><span class="sxs-lookup"><span data-stu-id="e6041-130">Execute whatever code is necessary for the particular verb that is associated with the  _iVerb_ parameter.</span></span> 
    
- <span data-ttu-id="e6041-131">如有必要, 请还原原始的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="e6041-131">If necessary, restore the original view context.</span></span>
    
- <span data-ttu-id="e6041-132">如果传入了未知动词号码, 则返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="e6041-132">If an unknown verb number was passed in, return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="e6041-133">否则, 根据执行的任何动作的成功或失败返回结果。</span><span class="sxs-lookup"><span data-stu-id="e6041-133">Otherwise, return a result based on the success or failure of whatever verb was executed.</span></span>
    
- <span data-ttu-id="e6041-134">关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="e6041-134">Close the form.</span></span> <span data-ttu-id="e6041-135">在**DoVerb**调用完成后, 始终负责关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="e6041-135">It is always your responsibility to close the form after a **DoVerb** call completes.</span></span> 
    
<span data-ttu-id="e6041-136">某些谓词 (如 Print) 应是有关**DoVerb**调用的模式, 也就是说, 在**DoVerb**调用返回之前, 必须完成指示的操作。</span><span class="sxs-lookup"><span data-stu-id="e6041-136">Some verbs, such as Print, should be modal with respect to the **DoVerb** call — that is, the indicated operation must be finished before the **DoVerb** call returns.</span></span> 
  
<span data-ttu-id="e6041-137">若要获取窗体窗口使用的**RECT**结构, 请调用[GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="e6041-137">To obtain the **RECT** structure used by a form's window, call the [GetWindowRect](https://msdn.microsoft.com/library/ms633519) function.</span></span> 
  
<span data-ttu-id="e6041-138">请勿将句柄保存在_hwndParent_参数中, 因为尽管它通常在**DoVerb**完成之前一直有效, 但它可以在调用返回时立即销毁。</span><span class="sxs-lookup"><span data-stu-id="e6041-138">Do not save the handle in the  _hwndParent_ parameter because, although it usually remains valid until the completion of **DoVerb**, it can be destroyed immediately upon the call's return.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e6041-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e6041-139">Notes to callers</span></span>

<span data-ttu-id="e6041-140">通过将_lpViewContext_指向从其[IMAPIViewContext:: GetViewStatus](imapiviewcontext-getviewstatus.md)方法返回 VCSTATUS_MODAL 标志的视图上下文实现, 可以使非模式谓词充当模式谓词。</span><span class="sxs-lookup"><span data-stu-id="e6041-140">You can make non-modal verbs act as modal verbs by pointing  _lpViewContext_ to a view context implementation that returns the VCSTATUS_MODAL flag from its [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
  
<span data-ttu-id="e6041-141">有关 MAPI 中的动词的详细信息, 请参阅[表单谓词](form-verbs.md)。</span><span class="sxs-lookup"><span data-stu-id="e6041-141">For more information about verbs in MAPI, see [Form Verbs](form-verbs.md).</span></span> <span data-ttu-id="e6041-142">有关如何在 ole 中处理谓词的详细信息, 请参阅[ole and Data Transfer](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e6041-142">For more information about how verbs are handled in OLE, see [OLE and Data Transfer](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e6041-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e6041-143">MFCMAPI reference</span></span>

<span data-ttu-id="e6041-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e6041-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e6041-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="e6041-145">**File**</span></span>|<span data-ttu-id="e6041-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="e6041-146">**Function**</span></span>|<span data-ttu-id="e6041-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="e6041-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6041-148">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="e6041-148">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="e6041-149">CMyMAPIFormViewer:: CallDoVerb</span><span class="sxs-lookup"><span data-stu-id="e6041-149">CMyMAPIFormViewer::CallDoVerb</span></span>  <br/> |<span data-ttu-id="e6041-150">MFCMAPI 使用**IMAPIForm::D overb**方法调用窗体上的谓词。</span><span class="sxs-lookup"><span data-stu-id="e6041-150">MFCMAPI uses the **IMAPIForm::DoVerb** method to invoke a verb on a form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e6041-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6041-151">See also</span></span>



[<span data-ttu-id="e6041-152">IMAPIForm::SetViewContext</span><span class="sxs-lookup"><span data-stu-id="e6041-152">IMAPIForm::SetViewContext</span></span>](imapiform-setviewcontext.md)
  
[<span data-ttu-id="e6041-153">IMAPIViewContext::GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="e6041-153">IMAPIViewContext::GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md)
  
[<span data-ttu-id="e6041-154">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e6041-154">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="e6041-155">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e6041-155">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="e6041-156">表单谓词</span><span class="sxs-lookup"><span data-stu-id="e6041-156">Form Verbs</span></span>](form-verbs.md)

