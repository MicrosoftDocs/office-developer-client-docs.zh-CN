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
ms.openlocfilehash: b481eaf00b7568da5f02ffa3301e8f2698a98e1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775436"
---
# <a name="imapiformmgrselectform"></a><span data-ttu-id="5478a-103">IMAPIFormMgr::SelectForm</span><span class="sxs-lookup"><span data-stu-id="5478a-103">IMAPIFormMgr::SelectForm</span></span>

  
  
<span data-ttu-id="5478a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5478a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5478a-105">显示一个对话框，允许用户选择一个窗体，并返回描述该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="5478a-105">Presents a dialog box that enables the user to select a form, and returns a form information object that describes that form.</span></span>
  
```cpp
HRESULT SelectForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFO FAR * ppfrminfoReturned
);
```

## <a name="parameters"></a><span data-ttu-id="5478a-106">参数</span><span class="sxs-lookup"><span data-stu-id="5478a-106">Parameters</span></span>

 <span data-ttu-id="5478a-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="5478a-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="5478a-108">[in]显示的对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="5478a-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="5478a-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5478a-109">_ulFlags_</span></span>
  
> <span data-ttu-id="5478a-110">[in]位掩码的标志的控制传入的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="5478a-110">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="5478a-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5478a-111">The following flag can be set:</span></span>
    
<span data-ttu-id="5478a-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5478a-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5478a-113">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5478a-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="5478a-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5478a-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="5478a-115">_pszTitle_</span><span class="sxs-lookup"><span data-stu-id="5478a-115">_pszTitle_</span></span>
  
> <span data-ttu-id="5478a-116">[in]一个指向一个字符串，包含对话框的标题。</span><span class="sxs-lookup"><span data-stu-id="5478a-116">[in] A pointer to a string that contains the caption of the dialog box.</span></span> <span data-ttu-id="5478a-117">如果_pszTitle_参数为 NULL，表单库提供程序提供的默认标题。</span><span class="sxs-lookup"><span data-stu-id="5478a-117">If the  _pszTitle_ parameter is NULL, the form library provider supplies a default caption.</span></span> 
    
 <span data-ttu-id="5478a-118">_pfld_</span><span class="sxs-lookup"><span data-stu-id="5478a-118">_pfld_</span></span>
  
> <span data-ttu-id="5478a-119">[in]指向文件夹从中选择窗体的指针。</span><span class="sxs-lookup"><span data-stu-id="5478a-119">[in] A pointer to the folder from which to select the form.</span></span> <span data-ttu-id="5478a-120">如果_pfld_参数为 NULL，则可以从本地、 个人，或组织窗体容器选择窗体。</span><span class="sxs-lookup"><span data-stu-id="5478a-120">If the  _pfld_ parameter is NULL, the form can be selected from the local, personal, or organization form container.</span></span> 
    
 <span data-ttu-id="5478a-121">_ppfrminfoReturned_</span><span class="sxs-lookup"><span data-stu-id="5478a-121">_ppfrminfoReturned_</span></span>
  
> <span data-ttu-id="5478a-122">[输出]指向返回窗体信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5478a-122">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5478a-123">返回值</span><span class="sxs-lookup"><span data-stu-id="5478a-123">Return value</span></span>

<span data-ttu-id="5478a-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="5478a-124">S_OK</span></span> 
  
> <span data-ttu-id="5478a-125">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="5478a-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="5478a-126">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="5478a-126">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="5478a-127">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="5478a-127">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="5478a-128">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="5478a-128">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="5478a-129">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="5478a-129">The user canceled the operation, typically by clicking the **Cancel** button in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5478a-130">说明</span><span class="sxs-lookup"><span data-stu-id="5478a-130">Remarks</span></span>

<span data-ttu-id="5478a-131">表单查看器调用**IMAPIFormMgr::SelectForm**方法向第一个存在一个对话框，允许用户选择一个窗体，然后检索窗体信息对象的介绍选定的窗体。</span><span class="sxs-lookup"><span data-stu-id="5478a-131">Form viewers call the **IMAPIFormMgr::SelectForm** method to first present a dialog box that enables the user to select a form and then to retrieve a form information object that describes the selected form.</span></span> <span data-ttu-id="5478a-132">对话框将约束用户选择单个窗体。</span><span class="sxs-lookup"><span data-stu-id="5478a-132">The dialog box constrains the user to select a single form.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5478a-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5478a-133">Notes to callers</span></span>

<span data-ttu-id="5478a-134">**SelectForm**对话框显示处于非隐藏状态的表单 （即，其隐藏属性的表单清除）。</span><span class="sxs-lookup"><span data-stu-id="5478a-134">The **SelectForm** dialog box displays only forms that are not hidden (that is, forms that have their hidden properties clear).</span></span> <span data-ttu-id="5478a-135">如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，所有字符串都是在 Unicode。</span><span class="sxs-lookup"><span data-stu-id="5478a-135">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings are Unicode.</span></span> <span data-ttu-id="5478a-136">如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="5478a-136">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5478a-137">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="5478a-137">MFCMAPI reference</span></span>

<span data-ttu-id="5478a-138">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5478a-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5478a-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="5478a-139">**File**</span></span>|<span data-ttu-id="5478a-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="5478a-140">**Function**</span></span>|<span data-ttu-id="5478a-141">**Comment**</span><span class="sxs-lookup"><span data-stu-id="5478a-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5478a-142">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="5478a-142">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="5478a-143">CFolderDlg::OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="5478a-143">CFolderDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="5478a-144">MFCMAPI 使用**IMAPIFormMgr::SelectForm**方法选择一个窗体，并将窗体的信息发送到一个或多个日志。</span><span class="sxs-lookup"><span data-stu-id="5478a-144">MFCMAPI uses the **IMAPIFormMgr::SelectForm** method to select a form and send information about the form to one or more logs.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5478a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5478a-145">See also</span></span>



[<span data-ttu-id="5478a-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5478a-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="5478a-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5478a-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

