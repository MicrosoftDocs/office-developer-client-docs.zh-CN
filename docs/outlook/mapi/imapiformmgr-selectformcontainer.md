---
title: IMAPIFormMgrSelectFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: c33daad6-52c4-4968-ac56-415178c9bf12
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bfddc24e6a9c7cf8bdeae1e5ea730ecdb116f564
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428590"
---
# <a name="imapiformmgrselectformcontainer"></a><span data-ttu-id="73c40-103">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="73c40-103">IMAPIFormMgr::SelectFormContainer</span></span>

  
  
<span data-ttu-id="73c40-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73c40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73c40-105">显示一个对话框，允许用户选择表单容器，并返回用户选择的容器对象的接口。</span><span class="sxs-lookup"><span data-stu-id="73c40-105">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="73c40-106">参数</span><span class="sxs-lookup"><span data-stu-id="73c40-106">Parameters</span></span>

 <span data-ttu-id="73c40-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="73c40-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="73c40-108">[in]所显示对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="73c40-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="73c40-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="73c40-109">_ulFlags_</span></span>
  
> <span data-ttu-id="73c40-110">[in]一个标志位掩码，用于控制如何选择表单库 (即，如何选择表单容器) 。</span><span class="sxs-lookup"><span data-stu-id="73c40-110">[in] A bitmask of flags that controls how the form library is selected (that is, how the form container is selected).</span></span> <span data-ttu-id="73c40-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="73c40-111">The following flags can be set:</span></span>
    
<span data-ttu-id="73c40-112">MAPIFORM_SELECT_ALL_REGISTRIES</span><span class="sxs-lookup"><span data-stu-id="73c40-112">MAPIFORM_SELECT_ALL_REGISTRIES</span></span> 
  
> <span data-ttu-id="73c40-113">可以从所有容器进行选择。</span><span class="sxs-lookup"><span data-stu-id="73c40-113">Selection can be made from all containers.</span></span> <span data-ttu-id="73c40-114">这是默认选择类型。</span><span class="sxs-lookup"><span data-stu-id="73c40-114">This is the default selection type.</span></span> 
    
<span data-ttu-id="73c40-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="73c40-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="73c40-116">只能从文件夹容器进行选择。</span><span class="sxs-lookup"><span data-stu-id="73c40-116">Selection can be made only from folder containers.</span></span>
    
<span data-ttu-id="73c40-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="73c40-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="73c40-118">只能从未与文件夹关联的容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="73c40-118">Selection can be made only from containers that are not associated with folders.</span></span>
    
 <span data-ttu-id="73c40-119">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="73c40-119">_lppfcnt_</span></span>
  
> <span data-ttu-id="73c40-120">[out]指向返回接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="73c40-120">[out] A pointer to a pointer to the returned interface.</span></span> <span data-ttu-id="73c40-121">此接口用于用户选择的容器对象。</span><span class="sxs-lookup"><span data-stu-id="73c40-121">This interface is for the container object that is selected by the user.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="73c40-122">返回值</span><span class="sxs-lookup"><span data-stu-id="73c40-122">Return value</span></span>

<span data-ttu-id="73c40-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="73c40-123">S_OK</span></span> 
  
> <span data-ttu-id="73c40-124">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="73c40-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="73c40-125">备注</span><span class="sxs-lookup"><span data-stu-id="73c40-125">Remarks</span></span>

<span data-ttu-id="73c40-126">表单查看器通常调用 **IMAPIFormMgr：：SelectFormContainer** 方法来选择将表单安装到的表单容器。</span><span class="sxs-lookup"><span data-stu-id="73c40-126">Form viewers typically call the **IMAPIFormMgr::SelectFormContainer** method to select a form container into which a form is installed.</span></span> <span data-ttu-id="73c40-127">**SelectFormContainer** 不能用于选择本地表单容器，该容器的值HFRMREG_LOCAL。</span><span class="sxs-lookup"><span data-stu-id="73c40-127">**SelectFormContainer** cannot be used to select the local form container, which has the value HFRMREG_LOCAL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="73c40-128">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="73c40-128">MFCMAPI reference</span></span>

<span data-ttu-id="73c40-129">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="73c40-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="73c40-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="73c40-130">**File**</span></span>|<span data-ttu-id="73c40-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="73c40-131">**Function**</span></span>|<span data-ttu-id="73c40-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="73c40-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73c40-133">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="73c40-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="73c40-134">CMainDlg：：OnSelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="73c40-134">CMainDlg::OnSelectFormContainer</span></span>  <br/> |<span data-ttu-id="73c40-135">MFCMAPI 使用 **IMAPIFormMgr：：SelectFormContainer** 方法在呈现表单容器内容之前选择表单容器。</span><span class="sxs-lookup"><span data-stu-id="73c40-135">MFCMAPI uses the **IMAPIFormMgr::SelectFormContainer** method to select a form container before rendering its contents.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="73c40-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73c40-136">See also</span></span>



[<span data-ttu-id="73c40-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="73c40-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="73c40-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="73c40-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

