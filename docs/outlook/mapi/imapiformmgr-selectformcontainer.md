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
ms.openlocfilehash: f66d0fb1fc9d252ff8b6985c4a54de79313266d1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577924"
---
# <a name="imapiformmgrselectformcontainer"></a><span data-ttu-id="a2ef9-103">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="a2ef9-103">IMAPIFormMgr::SelectFormContainer</span></span>

  
  
<span data-ttu-id="a2ef9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2ef9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2ef9-105">显示一个对话框，使用户能够选择窗体容器，并返回对 container 对象选定的用户界面。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-105">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="a2ef9-106">参数</span><span class="sxs-lookup"><span data-stu-id="a2ef9-106">Parameters</span></span>

 <span data-ttu-id="a2ef9-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a2ef9-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="a2ef9-108">[in]显示的对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="a2ef9-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a2ef9-109">_ulFlags_</span></span>
  
> <span data-ttu-id="a2ef9-110">[in]控制如何选择表单库的标志位掩码 （即，如何窗体容器选中）。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-110">[in] A bitmask of flags that controls how the form library is selected (that is, how the form container is selected).</span></span> <span data-ttu-id="a2ef9-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a2ef9-111">The following flags can be set:</span></span>
    
<span data-ttu-id="a2ef9-112">MAPIFORM_SELECT_ALL_REGISTRIES</span><span class="sxs-lookup"><span data-stu-id="a2ef9-112">MAPIFORM_SELECT_ALL_REGISTRIES</span></span> 
  
> <span data-ttu-id="a2ef9-113">可以从所有容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-113">Selection can be made from all containers.</span></span> <span data-ttu-id="a2ef9-114">这是默认所选内容类型。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-114">This is the default selection type.</span></span> 
    
<span data-ttu-id="a2ef9-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="a2ef9-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="a2ef9-116">可以仅从文件夹容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-116">Selection can be made only from folder containers.</span></span>
    
<span data-ttu-id="a2ef9-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="a2ef9-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="a2ef9-118">选定内容仅发出未与文件夹关联的容器。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-118">Selection can be made only from containers that are not associated with folders.</span></span>
    
 <span data-ttu-id="a2ef9-119">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="a2ef9-119">_lppfcnt_</span></span>
  
> <span data-ttu-id="a2ef9-120">[输出]指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-120">[out] A pointer to a pointer to the returned interface.</span></span> <span data-ttu-id="a2ef9-121">此接口是用户选择的容器对象。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-121">This interface is for the container object that is selected by the user.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a2ef9-122">返回值</span><span class="sxs-lookup"><span data-stu-id="a2ef9-122">Return value</span></span>

<span data-ttu-id="a2ef9-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2ef9-123">S_OK</span></span> 
  
> <span data-ttu-id="a2ef9-124">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a2ef9-125">注解</span><span class="sxs-lookup"><span data-stu-id="a2ef9-125">Remarks</span></span>

<span data-ttu-id="a2ef9-126">表单查看器通常调用**IMAPIFormMgr::SelectFormContainer**方法选择窗体所安装到一个窗体容器。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-126">Form viewers typically call the **IMAPIFormMgr::SelectFormContainer** method to select a form container into which a form is installed.</span></span> <span data-ttu-id="a2ef9-127">**SelectFormContainer**不能用于选择本地窗体的容器，具有 HFRMREG_LOCAL 的值。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-127">**SelectFormContainer** cannot be used to select the local form container, which has the value HFRMREG_LOCAL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a2ef9-128">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="a2ef9-128">MFCMAPI reference</span></span>

<span data-ttu-id="a2ef9-129">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a2ef9-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="a2ef9-130">**File**</span></span>|<span data-ttu-id="a2ef9-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="a2ef9-131">**Function**</span></span>|<span data-ttu-id="a2ef9-132">**Comment**</span><span class="sxs-lookup"><span data-stu-id="a2ef9-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2ef9-133">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="a2ef9-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="a2ef9-134">CMainDlg::OnSelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="a2ef9-134">CMainDlg::OnSelectFormContainer</span></span>  <br/> |<span data-ttu-id="a2ef9-135">MFCMAPI 使用**IMAPIFormMgr::SelectFormContainer**方法呈现其内容之前选择窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="a2ef9-135">MFCMAPI uses the **IMAPIFormMgr::SelectFormContainer** method to select a form container before rendering its contents.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a2ef9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2ef9-136">See also</span></span>



[<span data-ttu-id="a2ef9-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a2ef9-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="a2ef9-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a2ef9-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

