---
title: IMAPIFormMgrSelectMultipleForms
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.SelectMultipleForms
api_type:
- COM
ms.assetid: 172f8f53-b837-4286-9236-3f72806d7f1f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c40d853c49645638c2ec4001d86e64a1b2d2e381
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420309"
---
# <a name="imapiformmgrselectmultipleforms"></a><span data-ttu-id="54744-103">IMAPIFormMgr::SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="54744-103">IMAPIFormMgr::SelectMultipleForms</span></span>

  
  
<span data-ttu-id="54744-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54744-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54744-105">显示一个对话框，允许用户选择多个表单，并返回描述这些表单的表单信息对象数组。</span><span class="sxs-lookup"><span data-stu-id="54744-105">Presents a dialog box that enables the user to select multiple forms, and returns an array of form information objects that describe those forms.</span></span>
  
```cpp
HRESULT SelectMultipleForms(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFOARRAY pfrminfoarray,
  LPMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="54744-106">参数</span><span class="sxs-lookup"><span data-stu-id="54744-106">Parameters</span></span>

 <span data-ttu-id="54744-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="54744-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="54744-108">[in]所显示对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="54744-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="54744-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="54744-109">_ulFlags_</span></span>
  
> <span data-ttu-id="54744-110">[in]控制传入字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="54744-110">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="54744-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="54744-111">The following flag can be set:</span></span>
    
<span data-ttu-id="54744-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="54744-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="54744-113">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="54744-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="54744-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="54744-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="54744-115">_pszTitle_</span><span class="sxs-lookup"><span data-stu-id="54744-115">_pszTitle_</span></span>
  
> <span data-ttu-id="54744-116">[in]指向包含对话框标题的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="54744-116">[in] A pointer to a string that contains the caption of the dialog box.</span></span> <span data-ttu-id="54744-117">如果  _pszTitle_ 参数为 NULL，则提供表单的表单库提供程序将提供默认标题。</span><span class="sxs-lookup"><span data-stu-id="54744-117">If the  _pszTitle_ parameter is NULL, the form library provider that provides the forms supplies a default caption.</span></span> 
    
 <span data-ttu-id="54744-118">_pfld_</span><span class="sxs-lookup"><span data-stu-id="54744-118">_pfld_</span></span>
  
> <span data-ttu-id="54744-119">[in]指向从中选择窗体的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="54744-119">[in] A pointer to the folder from which to select the forms.</span></span> <span data-ttu-id="54744-120">如果  _pfld_ 参数为 NULL，则从本地、个人或组织表单容器中选择表单。</span><span class="sxs-lookup"><span data-stu-id="54744-120">If the  _pfld_ parameter is NULL, the forms are selected from the local, personal, or organization form container.</span></span> 
    
 <span data-ttu-id="54744-121">_pfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="54744-121">_pfrminfoarray_</span></span>
  
> <span data-ttu-id="54744-122">[in]指向预先为用户选择表单信息对象的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="54744-122">[in] A pointer to an array of form information objects that are preselected for the user.</span></span>
    
 <span data-ttu-id="54744-123">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="54744-123">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="54744-124">[out]指向返回的表单信息对象数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="54744-124">[out] A pointer to a pointer to the returned array of form information objects.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="54744-125">返回值</span><span class="sxs-lookup"><span data-stu-id="54744-125">Return value</span></span>

<span data-ttu-id="54744-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="54744-126">S_OK</span></span> 
  
> <span data-ttu-id="54744-127">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="54744-127">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="54744-128">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="54744-128">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="54744-129">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="54744-129">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="54744-130">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="54744-130">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="54744-131">用户通常通过单击对话框中的"取消 **"按钮来** 取消操作。</span><span class="sxs-lookup"><span data-stu-id="54744-131">The user canceled the operation, typically by clicking the **Cancel** button in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="54744-132">备注</span><span class="sxs-lookup"><span data-stu-id="54744-132">Remarks</span></span>

<span data-ttu-id="54744-133">表单查看器调用 **IMAPIFormMgr：：SelectMultipleForms** 方法，以首先显示一个对话框，使用户能够选择多个表单，然后检索描述所选表单的表单信息对象数组。</span><span class="sxs-lookup"><span data-stu-id="54744-133">Form viewers call the **IMAPIFormMgr::SelectMultipleForms** method to first present a dialog box that enables the user to select multiple forms and then to retrieve an array of form information objects that describe the selected forms.</span></span> <span data-ttu-id="54744-134">**SelectMultipleForms** 对话框显示所有窗体，无论它们是否 (，即其隐藏属性是否) 。</span><span class="sxs-lookup"><span data-stu-id="54744-134">The **SelectMultipleForms** dialog box displays all forms, whether or not they are hidden (that is, whether or not their hidden properties are clear).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="54744-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="54744-135">Notes to implementers</span></span>

<span data-ttu-id="54744-136">如果表单查看器在  _ulFlags_ MAPI_UNICODE传递该标志，则所有字符串都是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="54744-136">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings are Unicode.</span></span> <span data-ttu-id="54744-137">如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。</span><span class="sxs-lookup"><span data-stu-id="54744-137">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="54744-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54744-138">See also</span></span>



[<span data-ttu-id="54744-139">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="54744-139">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

