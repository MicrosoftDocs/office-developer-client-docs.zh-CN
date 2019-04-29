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
# <a name="imapiformmgrselectform"></a><span data-ttu-id="08018-103">IMAPIFormMgr::SelectForm</span><span class="sxs-lookup"><span data-stu-id="08018-103">IMAPIFormMgr::SelectForm</span></span>

  
  
<span data-ttu-id="08018-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08018-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08018-105">显示一个对话框, 使用户能够选择窗体, 并返回描述该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="08018-105">Presents a dialog box that enables the user to select a form, and returns a form information object that describes that form.</span></span>
  
```cpp
HRESULT SelectForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFO FAR * ppfrminfoReturned
);
```

## <a name="parameters"></a><span data-ttu-id="08018-106">参数</span><span class="sxs-lookup"><span data-stu-id="08018-106">Parameters</span></span>

 <span data-ttu-id="08018-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="08018-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="08018-108">实时显示的对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="08018-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="08018-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="08018-109">_ulFlags_</span></span>
  
> <span data-ttu-id="08018-110">实时标志的位掩码, 用于控制传入的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="08018-110">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="08018-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="08018-111">The following flag can be set:</span></span>
    
<span data-ttu-id="08018-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="08018-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="08018-113">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="08018-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="08018-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="08018-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="08018-115">_pszTitle_</span><span class="sxs-lookup"><span data-stu-id="08018-115">_pszTitle_</span></span>
  
> <span data-ttu-id="08018-116">实时指向包含对话框标题的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="08018-116">[in] A pointer to a string that contains the caption of the dialog box.</span></span> <span data-ttu-id="08018-117">如果_pszTitle_参数为 NULL, 则表单库提供程序将提供一个默认标题。</span><span class="sxs-lookup"><span data-stu-id="08018-117">If the  _pszTitle_ parameter is NULL, the form library provider supplies a default caption.</span></span> 
    
 <span data-ttu-id="08018-118">_pfld_</span><span class="sxs-lookup"><span data-stu-id="08018-118">_pfld_</span></span>
  
> <span data-ttu-id="08018-119">实时指向要从中选择表单的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="08018-119">[in] A pointer to the folder from which to select the form.</span></span> <span data-ttu-id="08018-120">如果_pfld_参数为 NULL, 则可以从 "本地"、"个人" 或 "组织" 表单容器中选择表单。</span><span class="sxs-lookup"><span data-stu-id="08018-120">If the  _pfld_ parameter is NULL, the form can be selected from the local, personal, or organization form container.</span></span> 
    
 <span data-ttu-id="08018-121">_ppfrminfoReturned_</span><span class="sxs-lookup"><span data-stu-id="08018-121">_ppfrminfoReturned_</span></span>
  
> <span data-ttu-id="08018-122">排除指向指向返回的表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="08018-122">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="08018-123">返回值</span><span class="sxs-lookup"><span data-stu-id="08018-123">Return value</span></span>

<span data-ttu-id="08018-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="08018-124">S_OK</span></span> 
  
> <span data-ttu-id="08018-125">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="08018-125">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="08018-126">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="08018-126">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="08018-127">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="08018-127">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="08018-128">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="08018-128">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="08018-129">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="08018-129">The user canceled the operation, typically by clicking the **Cancel** button in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="08018-130">说明</span><span class="sxs-lookup"><span data-stu-id="08018-130">Remarks</span></span>

<span data-ttu-id="08018-131">表单查看者调用**IMAPIFormMgr:: SelectForm**方法, 首先显示一个对话框, 使用户能够选择表单, 然后检索描述选定表单的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="08018-131">Form viewers call the **IMAPIFormMgr::SelectForm** method to first present a dialog box that enables the user to select a form and then to retrieve a form information object that describes the selected form.</span></span> <span data-ttu-id="08018-132">对话框限制用户选择单个窗体。</span><span class="sxs-lookup"><span data-stu-id="08018-132">The dialog box constrains the user to select a single form.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="08018-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="08018-133">Notes to callers</span></span>

<span data-ttu-id="08018-134">" **SelectForm** " 对话框仅显示未隐藏的表单 (即, 其隐藏属性已清除的表单)。</span><span class="sxs-lookup"><span data-stu-id="08018-134">The **SelectForm** dialog box displays only forms that are not hidden (that is, forms that have their hidden properties clear).</span></span> <span data-ttu-id="08018-135">如果表单查看器在_ulFlags_参数中传递 MAPI_UNICODE 标志, 则所有字符串均为 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="08018-135">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings are Unicode.</span></span> <span data-ttu-id="08018-136">如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="08018-136">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="08018-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="08018-137">MFCMAPI reference</span></span>

<span data-ttu-id="08018-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="08018-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="08018-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="08018-139">**File**</span></span>|<span data-ttu-id="08018-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="08018-140">**Function**</span></span>|<span data-ttu-id="08018-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="08018-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08018-142">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="08018-142">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="08018-143">CFolderDlg:: OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="08018-143">CFolderDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="08018-144">MFCMAPI 使用**IMAPIFormMgr:: SelectForm**方法选择窗体, 并将有关该窗体的信息发送到一个或多个日志。</span><span class="sxs-lookup"><span data-stu-id="08018-144">MFCMAPI uses the **IMAPIFormMgr::SelectForm** method to select a form and send information about the form to one or more logs.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="08018-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08018-145">See also</span></span>



[<span data-ttu-id="08018-146">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08018-146">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="08018-147">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="08018-147">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

