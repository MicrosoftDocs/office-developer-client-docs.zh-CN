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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321586"
---
# <a name="imapiformmgrselectformcontainer"></a><span data-ttu-id="bc3ad-103">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="bc3ad-103">IMAPIFormMgr::SelectFormContainer</span></span>

  
  
<span data-ttu-id="bc3ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc3ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc3ad-105">显示一个对话框, 使用户可以选择表单容器, 并为用户选定的容器对象返回一个接口。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-105">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="bc3ad-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc3ad-106">Parameters</span></span>

 <span data-ttu-id="bc3ad-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="bc3ad-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="bc3ad-108">实时显示的对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="bc3ad-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bc3ad-109">_ulFlags_</span></span>
  
> <span data-ttu-id="bc3ad-110">实时标志的位掩码, 用于控制表单库的选择方式 (即, 如何选择表单容器)。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-110">[in] A bitmask of flags that controls how the form library is selected (that is, how the form container is selected).</span></span> <span data-ttu-id="bc3ad-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="bc3ad-111">The following flags can be set:</span></span>
    
<span data-ttu-id="bc3ad-112">MAPIFORM_SELECT_ALL_REGISTRIES</span><span class="sxs-lookup"><span data-stu-id="bc3ad-112">MAPIFORM_SELECT_ALL_REGISTRIES</span></span> 
  
> <span data-ttu-id="bc3ad-113">可以从所有容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-113">Selection can be made from all containers.</span></span> <span data-ttu-id="bc3ad-114">这是默认选择类型。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-114">This is the default selection type.</span></span> 
    
<span data-ttu-id="bc3ad-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="bc3ad-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="bc3ad-116">只能从文件夹容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-116">Selection can be made only from folder containers.</span></span>
    
<span data-ttu-id="bc3ad-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="bc3ad-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="bc3ad-118">只能从与文件夹不关联的容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-118">Selection can be made only from containers that are not associated with folders.</span></span>
    
 <span data-ttu-id="bc3ad-119">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="bc3ad-119">_lppfcnt_</span></span>
  
> <span data-ttu-id="bc3ad-120">排除指向指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-120">[out] A pointer to a pointer to the returned interface.</span></span> <span data-ttu-id="bc3ad-121">此接口用于用户选择的容器对象。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-121">This interface is for the container object that is selected by the user.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc3ad-122">返回值</span><span class="sxs-lookup"><span data-stu-id="bc3ad-122">Return value</span></span>

<span data-ttu-id="bc3ad-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc3ad-123">S_OK</span></span> 
  
> <span data-ttu-id="bc3ad-124">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bc3ad-125">注解</span><span class="sxs-lookup"><span data-stu-id="bc3ad-125">Remarks</span></span>

<span data-ttu-id="bc3ad-126">表单查看器通常调用**IMAPIFormMgr:: SelectFormContainer**方法, 以选择要在其中安装表单的表单容器。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-126">Form viewers typically call the **IMAPIFormMgr::SelectFormContainer** method to select a form container into which a form is installed.</span></span> <span data-ttu-id="bc3ad-127">**SelectFormContainer**不能用于选择具有值 HFRMREG_LOCAL 的本地表单容器。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-127">**SelectFormContainer** cannot be used to select the local form container, which has the value HFRMREG_LOCAL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bc3ad-128">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="bc3ad-128">MFCMAPI reference</span></span>

<span data-ttu-id="bc3ad-129">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bc3ad-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="bc3ad-130">**File**</span></span>|<span data-ttu-id="bc3ad-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="bc3ad-131">**Function**</span></span>|<span data-ttu-id="bc3ad-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="bc3ad-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc3ad-133">MainDlg</span><span class="sxs-lookup"><span data-stu-id="bc3ad-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="bc3ad-134">CMainDlg:: OnSelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="bc3ad-134">CMainDlg::OnSelectFormContainer</span></span>  <br/> |<span data-ttu-id="bc3ad-135">MFCMAPI 使用**IMAPIFormMgr:: SelectFormContainer**方法在呈现表单容器的内容之前选择该表单容器。</span><span class="sxs-lookup"><span data-stu-id="bc3ad-135">MFCMAPI uses the **IMAPIFormMgr::SelectFormContainer** method to select a form container before rendering its contents.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bc3ad-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc3ad-136">See also</span></span>



[<span data-ttu-id="bc3ad-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc3ad-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="bc3ad-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bc3ad-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

