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
ms.openlocfilehash: ed3f793e4353cf78949a9df3a17dd3997a573f58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775421"
---
# <a name="imapiformmgrcreateform"></a><span data-ttu-id="c4707-103">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="c4707-103">IMAPIFormMgr::CreateForm</span></span>

  
  
<span data-ttu-id="c4707-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c4707-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c4707-105">打开一个窗体创建新邮件基于窗体的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="c4707-105">Opens a form to create a new message based on the form's message class.</span></span>
  
```cpp
HRESULT CreateForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  IMAPIFormInfo pfrminfoToActivate,
  REFIID refiidToAsk,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a><span data-ttu-id="c4707-106">参数</span><span class="sxs-lookup"><span data-stu-id="c4707-106">Parameters</span></span>

 <span data-ttu-id="c4707-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="c4707-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="c4707-108">[in]打开表单时显示进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="c4707-108">[in] A handle to the parent window for the progress indicator that is displayed while the form is opened.</span></span> <span data-ttu-id="c4707-109">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="c4707-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="c4707-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c4707-110">_ulFlags_</span></span>
  
> <span data-ttu-id="c4707-111">[in]位掩码的标志，控制如何打开表单。</span><span class="sxs-lookup"><span data-stu-id="c4707-111">[in] A bitmask of flags that controls how the form is opened.</span></span> <span data-ttu-id="c4707-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="c4707-112">The following flag can be set:</span></span>
    
<span data-ttu-id="c4707-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="c4707-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="c4707-114">显示用户界面，以提供状态或提示用户输入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4707-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="c4707-115">如果未设置此标志，将显示没有用户界面。</span><span class="sxs-lookup"><span data-stu-id="c4707-115">If this flag is not set, no user interface is displayed.</span></span>
    
 <span data-ttu-id="c4707-116">_pfrminfoToActivate_</span><span class="sxs-lookup"><span data-stu-id="c4707-116">_pfrminfoToActivate_</span></span>
  
> <span data-ttu-id="c4707-117">[in]指向用于打开窗体的窗体信息对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c4707-117">[in] A pointer to the form information object that is used to open the form.</span></span>
    
 <span data-ttu-id="c4707-118">_refiidToAsk_</span><span class="sxs-lookup"><span data-stu-id="c4707-118">_refiidToAsk_</span></span>
  
> <span data-ttu-id="c4707-119">[in]指向要为已创建的窗体对象返回的接口的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="c4707-119">[in] A pointer to the interface identifier (IID) for the interface to be returned for the form object that was created.</span></span> <span data-ttu-id="c4707-120">_RefiidToAsk_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c4707-120">The  _refiidToAsk_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="c4707-121">_ppvObj_</span><span class="sxs-lookup"><span data-stu-id="c4707-121">_ppvObj_</span></span>
  
> <span data-ttu-id="c4707-122">[输出]指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c4707-122">[out] A pointer to a pointer to the returned interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c4707-123">返回值</span><span class="sxs-lookup"><span data-stu-id="c4707-123">Return value</span></span>

<span data-ttu-id="c4707-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4707-124">S_OK</span></span> 
  
> <span data-ttu-id="c4707-125">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="c4707-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="c4707-126">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="c4707-126">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="c4707-127">通过 form 对象不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="c4707-127">The requested interface is not supported by the form object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c4707-128">说明</span><span class="sxs-lookup"><span data-stu-id="c4707-128">Remarks</span></span>

<span data-ttu-id="c4707-129">表单查看器调用**IMAPIFormMgr::CreateForm**方法打开要创建新邮件窗体的邮件类所基于的表单。</span><span class="sxs-lookup"><span data-stu-id="c4707-129">Form viewers call the **IMAPIFormMgr::CreateForm** method to open a form to create a new message based on the form's message class.</span></span> <span data-ttu-id="c4707-130">**CreateForm**通过给定窗体信息对象中所述创建该窗体的窗体服务器实例中打开该窗体。</span><span class="sxs-lookup"><span data-stu-id="c4707-130">**CreateForm** opens the form by creating an instance of the form server for that form as described in the given form information object.</span></span> <span data-ttu-id="c4707-131">如果需要， **CreateForm**调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)方法下载到用户的磁盘的窗体服务器代码。</span><span class="sxs-lookup"><span data-stu-id="c4707-131">If required, **CreateForm** calls the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) method to download the form server code to the user's disk.</span></span> 
  
<span data-ttu-id="c4707-132">_PfrminfoToActivate_参数必须指向窗体信息对象中已正确解析。</span><span class="sxs-lookup"><span data-stu-id="c4707-132">The  _pfrminfoToActivate_ parameter must point to a form information object that has been correctly resolved.</span></span> 
  
<span data-ttu-id="c4707-133">在打开窗体后，调用表单查看器必须设置使用[IPersistMessage](ipersistmessageiunknown.md)界面的一条消息，并且可以根据需要设置表单视图上下文。</span><span class="sxs-lookup"><span data-stu-id="c4707-133">After the form has been opened, the calling form viewer must set up a message by using the [IPersistMessage](ipersistmessageiunknown.md) interface and can optionally set up a view context for the form.</span></span> <span data-ttu-id="c4707-134">有关详细信息，请参阅[启动窗体服务器](launching-a-form-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c4707-134">For more information, see [Launching a Form Server](launching-a-form-server.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c4707-135">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c4707-135">MFCMAPI reference</span></span>

<span data-ttu-id="c4707-136">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c4707-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c4707-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="c4707-137">**File**</span></span>|<span data-ttu-id="c4707-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="c4707-138">**Function**</span></span>|<span data-ttu-id="c4707-139">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c4707-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4707-140">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="c4707-140">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="c4707-141">CreateAndDisplayNewMailInFolder</span><span class="sxs-lookup"><span data-stu-id="c4707-141">CreateAndDisplayNewMailInFolder</span></span>  <br/> |<span data-ttu-id="c4707-142">MFCMAPI 使用**IMAPIFormMgr::CreateForm**方法显示之前创建的表单。</span><span class="sxs-lookup"><span data-stu-id="c4707-142">MFCMAPI uses the **IMAPIFormMgr::CreateForm** method to create a form before displaying it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c4707-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4707-143">See also</span></span>



[<span data-ttu-id="c4707-144">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="c4707-144">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="c4707-145">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4707-145">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="c4707-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4707-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="c4707-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c4707-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="c4707-148">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="c4707-148">Launching a Form Server</span></span>](launching-a-form-server.md)

