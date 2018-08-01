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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 096437f10c5b992a1db55f6a856c38021a81b99a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775452"
---
# <a name="imapiformmgrselectmultipleforms"></a><span data-ttu-id="68e7b-103">IMAPIFormMgr::SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="68e7b-103">IMAPIFormMgr::SelectMultipleForms</span></span>

  
  
<span data-ttu-id="68e7b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="68e7b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="68e7b-105">显示一个对话框，使用户能够选择多个表单，并返回介绍这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="68e7b-105">Presents a dialog box that enables the user to select multiple forms, and returns an array of form information objects that describe those forms.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="68e7b-106">参数</span><span class="sxs-lookup"><span data-stu-id="68e7b-106">Parameters</span></span>

 <span data-ttu-id="68e7b-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="68e7b-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="68e7b-108">[in]显示的对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="68e7b-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="68e7b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="68e7b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="68e7b-110">[in]位掩码的标志的控制传入的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="68e7b-110">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="68e7b-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="68e7b-111">The following flag can be set:</span></span>
    
<span data-ttu-id="68e7b-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="68e7b-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="68e7b-113">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="68e7b-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="68e7b-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="68e7b-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="68e7b-115">_pszTitle_</span><span class="sxs-lookup"><span data-stu-id="68e7b-115">_pszTitle_</span></span>
  
> <span data-ttu-id="68e7b-116">[in]一个指向一个字符串，包含对话框的标题。</span><span class="sxs-lookup"><span data-stu-id="68e7b-116">[in] A pointer to a string that contains the caption of the dialog box.</span></span> <span data-ttu-id="68e7b-117">如果_pszTitle_参数为 NULL，提供窗体的窗体库提供程序提供的默认标题。</span><span class="sxs-lookup"><span data-stu-id="68e7b-117">If the  _pszTitle_ parameter is NULL, the form library provider that provides the forms supplies a default caption.</span></span> 
    
 <span data-ttu-id="68e7b-118">_pfld_</span><span class="sxs-lookup"><span data-stu-id="68e7b-118">_pfld_</span></span>
  
> <span data-ttu-id="68e7b-119">[in]指向文件夹从中选择窗体的指针。</span><span class="sxs-lookup"><span data-stu-id="68e7b-119">[in] A pointer to the folder from which to select the forms.</span></span> <span data-ttu-id="68e7b-120">如果_pfld_参数为 NULL，则从本地、 个人，或组织窗体容器中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="68e7b-120">If the  _pfld_ parameter is NULL, the forms are selected from the local, personal, or organization form container.</span></span> 
    
 <span data-ttu-id="68e7b-121">_pfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="68e7b-121">_pfrminfoarray_</span></span>
  
> <span data-ttu-id="68e7b-122">[in]一个指向未预先选择用户的窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="68e7b-122">[in] A pointer to an array of form information objects that are preselected for the user.</span></span>
    
 <span data-ttu-id="68e7b-123">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="68e7b-123">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="68e7b-124">[输出]指向到窗体信息对象返回的数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="68e7b-124">[out] A pointer to a pointer to the returned array of form information objects.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="68e7b-125">返回值</span><span class="sxs-lookup"><span data-stu-id="68e7b-125">Return value</span></span>

<span data-ttu-id="68e7b-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="68e7b-126">S_OK</span></span> 
  
> <span data-ttu-id="68e7b-127">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="68e7b-127">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="68e7b-128">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="68e7b-128">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="68e7b-129">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="68e7b-129">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="68e7b-130">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="68e7b-130">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="68e7b-131">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="68e7b-131">The user canceled the operation, typically by clicking the **Cancel** button in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="68e7b-132">说明</span><span class="sxs-lookup"><span data-stu-id="68e7b-132">Remarks</span></span>

<span data-ttu-id="68e7b-133">表单查看器调用**IMAPIFormMgr::SelectMultipleForms**方法到第一个存在一个对话框，使用户能够选择多个窗体，然后检索数组表单信息的对象的描述所选的形式。</span><span class="sxs-lookup"><span data-stu-id="68e7b-133">Form viewers call the **IMAPIFormMgr::SelectMultipleForms** method to first present a dialog box that enables the user to select multiple forms and then to retrieve an array of form information objects that describe the selected forms.</span></span> <span data-ttu-id="68e7b-134">**SelectMultipleForms**对话框中显示所有窗体，它们处于隐藏状态 （也就是说，不管其隐藏的属性清除)。</span><span class="sxs-lookup"><span data-stu-id="68e7b-134">The **SelectMultipleForms** dialog box displays all forms, whether or not they are hidden (that is, whether or not their hidden properties are clear).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="68e7b-135">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="68e7b-135">Notes to implementers</span></span>

<span data-ttu-id="68e7b-136">如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，所有字符串都是在 Unicode。</span><span class="sxs-lookup"><span data-stu-id="68e7b-136">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings are Unicode.</span></span> <span data-ttu-id="68e7b-137">如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="68e7b-137">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="68e7b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68e7b-138">See also</span></span>



[<span data-ttu-id="68e7b-139">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="68e7b-139">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

