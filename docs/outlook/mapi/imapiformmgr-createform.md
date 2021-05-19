---
title: IMAPIFormMgrCreateForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.CreateForm
api_type:
- COM
ms.assetid: 7d4d50f8-3904-4e93-a535-ac7decceb1a3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c6e18ee9f8ea1d7dc6592d576c5a1163db526639
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419847"
---
# <a name="imapiformmgrcreateform"></a><span data-ttu-id="f18fd-103">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="f18fd-103">IMAPIFormMgr::CreateForm</span></span>

  
  
<span data-ttu-id="f18fd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f18fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f18fd-105">打开窗体以基于窗体的邮件类创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="f18fd-105">Opens a form to create a new message based on the form's message class.</span></span>
  
```cpp
HRESULT CreateForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  IMAPIFormInfo pfrminfoToActivate,
  REFIID refiidToAsk,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a><span data-ttu-id="f18fd-106">参数</span><span class="sxs-lookup"><span data-stu-id="f18fd-106">Parameters</span></span>

 <span data-ttu-id="f18fd-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="f18fd-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="f18fd-108">[in]打开窗体时显示的进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="f18fd-108">[in] A handle to the parent window for the progress indicator that is displayed while the form is opened.</span></span> <span data-ttu-id="f18fd-109">除非  _在 ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="f18fd-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="f18fd-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f18fd-110">_ulFlags_</span></span>
  
> <span data-ttu-id="f18fd-111">[in]控制表单打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f18fd-111">[in] A bitmask of flags that controls how the form is opened.</span></span> <span data-ttu-id="f18fd-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f18fd-112">The following flag can be set:</span></span>
    
<span data-ttu-id="f18fd-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="f18fd-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="f18fd-114">显示用户界面以提供状态或提示用户输入详细信息。</span><span class="sxs-lookup"><span data-stu-id="f18fd-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="f18fd-115">如果未设置此标志，则不显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="f18fd-115">If this flag is not set, no user interface is displayed.</span></span>
    
 <span data-ttu-id="f18fd-116">_pfrminfoToActivate_</span><span class="sxs-lookup"><span data-stu-id="f18fd-116">_pfrminfoToActivate_</span></span>
  
> <span data-ttu-id="f18fd-117">[in]指向用于打开窗体的窗体信息对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f18fd-117">[in] A pointer to the form information object that is used to open the form.</span></span>
    
 <span data-ttu-id="f18fd-118">_refiidToAsk_</span><span class="sxs-lookup"><span data-stu-id="f18fd-118">_refiidToAsk_</span></span>
  
> <span data-ttu-id="f18fd-119">[in]指向接口标识符的 (IID) ，用于为创建的表单对象返回接口。</span><span class="sxs-lookup"><span data-stu-id="f18fd-119">[in] A pointer to the interface identifier (IID) for the interface to be returned for the form object that was created.</span></span> <span data-ttu-id="f18fd-120">_refiidToAsk_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f18fd-120">The  _refiidToAsk_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="f18fd-121">_ppvObj_</span><span class="sxs-lookup"><span data-stu-id="f18fd-121">_ppvObj_</span></span>
  
> <span data-ttu-id="f18fd-122">[out]指向返回接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f18fd-122">[out] A pointer to a pointer to the returned interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f18fd-123">返回值</span><span class="sxs-lookup"><span data-stu-id="f18fd-123">Return value</span></span>

<span data-ttu-id="f18fd-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="f18fd-124">S_OK</span></span> 
  
> <span data-ttu-id="f18fd-125">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="f18fd-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f18fd-126">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f18fd-126">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="f18fd-127">请求的接口不受 form 对象支持。</span><span class="sxs-lookup"><span data-stu-id="f18fd-127">The requested interface is not supported by the form object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f18fd-128">备注</span><span class="sxs-lookup"><span data-stu-id="f18fd-128">Remarks</span></span>

<span data-ttu-id="f18fd-129">表单查看者调用 **IMAPIFormMgr：：CreateForm** 方法以打开表单以基于表单的邮件类创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="f18fd-129">Form viewers call the **IMAPIFormMgr::CreateForm** method to open a form to create a new message based on the form's message class.</span></span> <span data-ttu-id="f18fd-130">**CreateForm** 通过创建该窗体的窗体服务器实例来打开该窗体，如给定窗体信息对象中所述。</span><span class="sxs-lookup"><span data-stu-id="f18fd-130">**CreateForm** opens the form by creating an instance of the form server for that form as described in the given form information object.</span></span> <span data-ttu-id="f18fd-131">如果需要 **，CreateForm** 将调用 [IMAPIFormMgr：:P repareForm](imapiformmgr-prepareform.md) 方法将表单服务器代码下载到用户的磁盘。</span><span class="sxs-lookup"><span data-stu-id="f18fd-131">If required, **CreateForm** calls the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) method to download the form server code to the user's disk.</span></span> 
  
<span data-ttu-id="f18fd-132">_pfrminfoToActivate_ 参数必须指向已正确解析的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="f18fd-132">The  _pfrminfoToActivate_ parameter must point to a form information object that has been correctly resolved.</span></span> 
  
<span data-ttu-id="f18fd-133">打开表单后，调用表单查看器必须使用 [IPersistMessage](ipersistmessageiunknown.md) 接口设置邮件，并且可以选择为表单设置视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f18fd-133">After the form has been opened, the calling form viewer must set up a message by using the [IPersistMessage](ipersistmessageiunknown.md) interface and can optionally set up a view context for the form.</span></span> <span data-ttu-id="f18fd-134">有关详细信息，请参阅 [启动窗体服务器](launching-a-form-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f18fd-134">For more information, see [Launching a Form Server](launching-a-form-server.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f18fd-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f18fd-135">MFCMAPI reference</span></span>

<span data-ttu-id="f18fd-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f18fd-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f18fd-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="f18fd-137">**File**</span></span>|<span data-ttu-id="f18fd-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="f18fd-138">**Function**</span></span>|<span data-ttu-id="f18fd-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="f18fd-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f18fd-140">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="f18fd-140">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="f18fd-141">CreateAndDisplayNewMailInFolder</span><span class="sxs-lookup"><span data-stu-id="f18fd-141">CreateAndDisplayNewMailInFolder</span></span>  <br/> |<span data-ttu-id="f18fd-142">MFCMAPI 使用 **IMAPIFormMgr：：CreateForm** 方法在显示表单之前创建表单。</span><span class="sxs-lookup"><span data-stu-id="f18fd-142">MFCMAPI uses the **IMAPIFormMgr::CreateForm** method to create a form before displaying it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f18fd-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f18fd-143">See also</span></span>



[<span data-ttu-id="f18fd-144">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="f18fd-144">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="f18fd-145">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f18fd-145">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="f18fd-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f18fd-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="f18fd-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f18fd-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="f18fd-148">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="f18fd-148">Launching a Form Server</span></span>](launching-a-form-server.md)

