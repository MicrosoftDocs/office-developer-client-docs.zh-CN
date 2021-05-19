---
title: IMAPIFormMgrSelectForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.SelectForm
api_type:
- COM
ms.assetid: c1cfe71b-01f3-429a-8b4c-73191a2ffea0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c25f352e7fa607a46741164574a4ba91d4026edf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423578"
---
# <a name="imapiformmgrselectform"></a><span data-ttu-id="bd693-103">IMAPIFormMgr::SelectForm</span><span class="sxs-lookup"><span data-stu-id="bd693-103">IMAPIFormMgr::SelectForm</span></span>

  
  
<span data-ttu-id="bd693-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bd693-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bd693-105">显示一个对话框，允许用户选择一个窗体，并返回描述该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="bd693-105">Presents a dialog box that enables the user to select a form, and returns a form information object that describes that form.</span></span>
  
```cpp
HRESULT SelectForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFO FAR * ppfrminfoReturned
);
```

## <a name="parameters"></a><span data-ttu-id="bd693-106">参数</span><span class="sxs-lookup"><span data-stu-id="bd693-106">Parameters</span></span>

 <span data-ttu-id="bd693-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="bd693-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="bd693-108">[in]所显示对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bd693-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="bd693-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bd693-109">_ulFlags_</span></span>
  
> <span data-ttu-id="bd693-110">[in]控制传入字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="bd693-110">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="bd693-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="bd693-111">The following flag can be set:</span></span>
    
<span data-ttu-id="bd693-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="bd693-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="bd693-113">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="bd693-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="bd693-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="bd693-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="bd693-115">_pszTitle_</span><span class="sxs-lookup"><span data-stu-id="bd693-115">_pszTitle_</span></span>
  
> <span data-ttu-id="bd693-116">[in]指向包含对话框标题的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="bd693-116">[in] A pointer to a string that contains the caption of the dialog box.</span></span> <span data-ttu-id="bd693-117">如果  _pszTitle_ 参数为 NULL，则表单库提供程序会提供默认标题。</span><span class="sxs-lookup"><span data-stu-id="bd693-117">If the  _pszTitle_ parameter is NULL, the form library provider supplies a default caption.</span></span> 
    
 <span data-ttu-id="bd693-118">_pfld_</span><span class="sxs-lookup"><span data-stu-id="bd693-118">_pfld_</span></span>
  
> <span data-ttu-id="bd693-119">[in]指向从中选择窗体的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="bd693-119">[in] A pointer to the folder from which to select the form.</span></span> <span data-ttu-id="bd693-120">如果  _pfld_ 参数为 NULL，可以从本地、个人或组织表单容器选择表单。</span><span class="sxs-lookup"><span data-stu-id="bd693-120">If the  _pfld_ parameter is NULL, the form can be selected from the local, personal, or organization form container.</span></span> 
    
 <span data-ttu-id="bd693-121">_ppfrminfoReturned_</span><span class="sxs-lookup"><span data-stu-id="bd693-121">_ppfrminfoReturned_</span></span>
  
> <span data-ttu-id="bd693-122">[out]指向返回的表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bd693-122">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bd693-123">返回值</span><span class="sxs-lookup"><span data-stu-id="bd693-123">Return value</span></span>

<span data-ttu-id="bd693-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd693-124">S_OK</span></span> 
  
> <span data-ttu-id="bd693-125">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="bd693-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="bd693-126">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="bd693-126">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="bd693-127">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bd693-127">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="bd693-128">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="bd693-128">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="bd693-129">用户通常通过单击对话框中的"取消 **"按钮来** 取消操作。</span><span class="sxs-lookup"><span data-stu-id="bd693-129">The user canceled the operation, typically by clicking the **Cancel** button in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="bd693-130">备注</span><span class="sxs-lookup"><span data-stu-id="bd693-130">Remarks</span></span>

<span data-ttu-id="bd693-131">表单查看者调用 **IMAPIFormMgr：：SelectForm** 方法，以首先显示一个对话框，使用户可以选择一个表单，然后检索描述所选表单的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="bd693-131">Form viewers call the **IMAPIFormMgr::SelectForm** method to first present a dialog box that enables the user to select a form and then to retrieve a form information object that describes the selected form.</span></span> <span data-ttu-id="bd693-132">该对话框将限制用户选择单个窗体。</span><span class="sxs-lookup"><span data-stu-id="bd693-132">The dialog box constrains the user to select a single form.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="bd693-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="bd693-133">Notes to callers</span></span>

<span data-ttu-id="bd693-134">**"SelectForm"** 对话框仅显示未隐藏 (，即具有隐藏属性的表单) 。</span><span class="sxs-lookup"><span data-stu-id="bd693-134">The **SelectForm** dialog box displays only forms that are not hidden (that is, forms that have their hidden properties clear).</span></span> <span data-ttu-id="bd693-135">如果表单查看器在  _ulFlags_ MAPI_UNICODE传递该标志，则所有字符串都是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bd693-135">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings are Unicode.</span></span> <span data-ttu-id="bd693-136">如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。</span><span class="sxs-lookup"><span data-stu-id="bd693-136">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bd693-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="bd693-137">MFCMAPI reference</span></span>

<span data-ttu-id="bd693-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bd693-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bd693-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="bd693-139">**File**</span></span>|<span data-ttu-id="bd693-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="bd693-140">**Function**</span></span>|<span data-ttu-id="bd693-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="bd693-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd693-142">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="bd693-142">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="bd693-143">CFolderDlg：：OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="bd693-143">CFolderDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="bd693-144">MFCMAPI 使用 **IMAPIFormMgr：：SelectForm** 方法选择表单并将有关表单的信息发送到一个或多个日志。</span><span class="sxs-lookup"><span data-stu-id="bd693-144">MFCMAPI uses the **IMAPIFormMgr::SelectForm** method to select a form and send information about the form to one or more logs.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bd693-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd693-145">See also</span></span>



[<span data-ttu-id="bd693-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bd693-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="bd693-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bd693-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

