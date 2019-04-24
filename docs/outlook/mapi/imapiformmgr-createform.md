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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321663"
---
# <a name="imapiformmgrcreateform"></a><span data-ttu-id="a4be4-103">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="a4be4-103">IMAPIFormMgr::CreateForm</span></span>

  
  
<span data-ttu-id="a4be4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4be4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4be4-105">打开一个窗体, 以根据窗体的邮件类创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="a4be4-105">Opens a form to create a new message based on the form's message class.</span></span>
  
```cpp
HRESULT CreateForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  IMAPIFormInfo pfrminfoToActivate,
  REFIID refiidToAsk,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a><span data-ttu-id="a4be4-106">参数</span><span class="sxs-lookup"><span data-stu-id="a4be4-106">Parameters</span></span>

 <span data-ttu-id="a4be4-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a4be4-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="a4be4-108">实时在打开表单时显示的进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a4be4-108">[in] A handle to the parent window for the progress indicator that is displayed while the form is opened.</span></span> <span data-ttu-id="a4be4-109">除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="a4be4-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="a4be4-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a4be4-110">_ulFlags_</span></span>
  
> <span data-ttu-id="a4be4-111">实时用于控制表单打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a4be4-111">[in] A bitmask of flags that controls how the form is opened.</span></span> <span data-ttu-id="a4be4-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a4be4-112">The following flag can be set:</span></span>
    
<span data-ttu-id="a4be4-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a4be4-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="a4be4-114">显示一个用户界面, 以提供状态或提示用户详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4be4-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="a4be4-115">如果未设置此标志, 则不会显示任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="a4be4-115">If this flag is not set, no user interface is displayed.</span></span>
    
 <span data-ttu-id="a4be4-116">_pfrminfoToActivate_</span><span class="sxs-lookup"><span data-stu-id="a4be4-116">_pfrminfoToActivate_</span></span>
  
> <span data-ttu-id="a4be4-117">实时指向表单信息对象的指针, 该对象用于打开表单。</span><span class="sxs-lookup"><span data-stu-id="a4be4-117">[in] A pointer to the form information object that is used to open the form.</span></span>
    
 <span data-ttu-id="a4be4-118">_refiidToAsk_</span><span class="sxs-lookup"><span data-stu-id="a4be4-118">_refiidToAsk_</span></span>
  
> <span data-ttu-id="a4be4-119">实时指向接口标识符 (IID) 的指针, 该接口标识符将为所创建的 form 对象返回。</span><span class="sxs-lookup"><span data-stu-id="a4be4-119">[in] A pointer to the interface identifier (IID) for the interface to be returned for the form object that was created.</span></span> <span data-ttu-id="a4be4-120">_refiidToAsk_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a4be4-120">The  _refiidToAsk_ parameter must not be NULL.</span></span> 
    
 <span data-ttu-id="a4be4-121">_ppvObj_</span><span class="sxs-lookup"><span data-stu-id="a4be4-121">_ppvObj_</span></span>
  
> <span data-ttu-id="a4be4-122">排除指向指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a4be4-122">[out] A pointer to a pointer to the returned interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a4be4-123">返回值</span><span class="sxs-lookup"><span data-stu-id="a4be4-123">Return value</span></span>

<span data-ttu-id="a4be4-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4be4-124">S_OK</span></span> 
  
> <span data-ttu-id="a4be4-125">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a4be4-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="a4be4-126">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="a4be4-126">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="a4be4-127">表单对象不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="a4be4-127">The requested interface is not supported by the form object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a4be4-128">注解</span><span class="sxs-lookup"><span data-stu-id="a4be4-128">Remarks</span></span>

<span data-ttu-id="a4be4-129">表单查看者调用**IMAPIFormMgr:: CreateForm**方法打开一个窗体, 以根据窗体的邮件类创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="a4be4-129">Form viewers call the **IMAPIFormMgr::CreateForm** method to open a form to create a new message based on the form's message class.</span></span> <span data-ttu-id="a4be4-130">**CreateForm**通过为该窗体创建窗体服务器的一个实例来打开该窗体, 如给定的窗体信息对象中所述。</span><span class="sxs-lookup"><span data-stu-id="a4be4-130">**CreateForm** opens the form by creating an instance of the form server for that form as described in the given form information object.</span></span> <span data-ttu-id="a4be4-131">如果需要, **CreateForm**调用[IMAPIFormMgr::P repareform](imapiformmgr-prepareform.md)方法将表单服务器代码下载到用户磁盘。</span><span class="sxs-lookup"><span data-stu-id="a4be4-131">If required, **CreateForm** calls the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) method to download the form server code to the user's disk.</span></span> 
  
<span data-ttu-id="a4be4-132">_pfrminfoToActivate_参数必须指向已正确解析的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="a4be4-132">The  _pfrminfoToActivate_ parameter must point to a form information object that has been correctly resolved.</span></span> 
  
<span data-ttu-id="a4be4-133">打开窗体后, 调用表单查看器必须使用[IPersistMessage](ipersistmessageiunknown.md)接口设置邮件, 并且可以选择设置窗体的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="a4be4-133">After the form has been opened, the calling form viewer must set up a message by using the [IPersistMessage](ipersistmessageiunknown.md) interface and can optionally set up a view context for the form.</span></span> <span data-ttu-id="a4be4-134">有关详细信息, 请参阅[启动表单服务器](launching-a-form-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a4be4-134">For more information, see [Launching a Form Server](launching-a-form-server.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a4be4-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a4be4-135">MFCMAPI reference</span></span>

<span data-ttu-id="a4be4-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a4be4-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a4be4-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="a4be4-137">**File**</span></span>|<span data-ttu-id="a4be4-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="a4be4-138">**Function**</span></span>|<span data-ttu-id="a4be4-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="a4be4-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4be4-140">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="a4be4-140">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="a4be4-141">CreateAndDisplayNewMailInFolder</span><span class="sxs-lookup"><span data-stu-id="a4be4-141">CreateAndDisplayNewMailInFolder</span></span>  <br/> |<span data-ttu-id="a4be4-142">MFCMAPI 使用**IMAPIFormMgr:: CreateForm**方法在显示窗体之前创建窗体。</span><span class="sxs-lookup"><span data-stu-id="a4be4-142">MFCMAPI uses the **IMAPIFormMgr::CreateForm** method to create a form before displaying it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a4be4-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4be4-143">See also</span></span>



[<span data-ttu-id="a4be4-144">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="a4be4-144">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="a4be4-145">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4be4-145">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="a4be4-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4be4-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="a4be4-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a4be4-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="a4be4-148">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="a4be4-148">Launching a Form Server</span></span>](launching-a-form-server.md)

