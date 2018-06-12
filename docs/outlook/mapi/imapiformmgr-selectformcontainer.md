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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ef9b99f06b62fd361bb780debb527ec2d7457589
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775460"
---
# <a name="imapiformmgrselectformcontainer"></a><span data-ttu-id="45594-103">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="45594-103">IMAPIFormMgr::SelectFormContainer</span></span>

  
  
<span data-ttu-id="45594-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="45594-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="45594-105">显示一个对话框，使用户能够选择窗体容器，并返回对 container 对象选定的用户界面。</span><span class="sxs-lookup"><span data-stu-id="45594-105">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="45594-106">参数</span><span class="sxs-lookup"><span data-stu-id="45594-106">Parameters</span></span>

 <span data-ttu-id="45594-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="45594-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="45594-108">[in]显示的对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="45594-108">[in] A handle to the parent window of the displayed dialog box.</span></span> 
    
 <span data-ttu-id="45594-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="45594-109">_ulFlags_</span></span>
  
> <span data-ttu-id="45594-110">[in]控制如何选择表单库的标志位掩码 （即，如何窗体容器选中）。</span><span class="sxs-lookup"><span data-stu-id="45594-110">[in] A bitmask of flags that controls how the form library is selected (that is, how the form container is selected).</span></span> <span data-ttu-id="45594-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="45594-111">The following flags can be set:</span></span>
    
<span data-ttu-id="45594-112">MAPIFORM_SELECT_ALL_REGISTRIES</span><span class="sxs-lookup"><span data-stu-id="45594-112">MAPIFORM_SELECT_ALL_REGISTRIES</span></span> 
  
> <span data-ttu-id="45594-113">可以从所有容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="45594-113">Selection can be made from all containers.</span></span> <span data-ttu-id="45594-114">这是默认所选内容类型。</span><span class="sxs-lookup"><span data-stu-id="45594-114">This is the default selection type.</span></span> 
    
<span data-ttu-id="45594-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="45594-115">MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="45594-116">可以仅从文件夹容器中进行选择。</span><span class="sxs-lookup"><span data-stu-id="45594-116">Selection can be made only from folder containers.</span></span>
    
<span data-ttu-id="45594-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span><span class="sxs-lookup"><span data-stu-id="45594-117">MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY</span></span> 
  
> <span data-ttu-id="45594-118">选定内容仅发出未与文件夹关联的容器。</span><span class="sxs-lookup"><span data-stu-id="45594-118">Selection can be made only from containers that are not associated with folders.</span></span>
    
 <span data-ttu-id="45594-119">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="45594-119">_lppfcnt_</span></span>
  
> <span data-ttu-id="45594-120">[输出]指向返回的接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="45594-120">[out] A pointer to a pointer to the returned interface.</span></span> <span data-ttu-id="45594-121">此接口是用户选择的容器对象。</span><span class="sxs-lookup"><span data-stu-id="45594-121">This interface is for the container object that is selected by the user.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="45594-122">返回值</span><span class="sxs-lookup"><span data-stu-id="45594-122">Return value</span></span>

<span data-ttu-id="45594-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="45594-123">S_OK</span></span> 
  
> <span data-ttu-id="45594-124">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="45594-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="45594-125">备注</span><span class="sxs-lookup"><span data-stu-id="45594-125">Remarks</span></span>

<span data-ttu-id="45594-126">表单查看器通常调用**IMAPIFormMgr::SelectFormContainer**方法选择窗体所安装到一个窗体容器。</span><span class="sxs-lookup"><span data-stu-id="45594-126">Form viewers typically call the **IMAPIFormMgr::SelectFormContainer** method to select a form container into which a form is installed.</span></span> <span data-ttu-id="45594-127">**SelectFormContainer**不能用于选择本地窗体的容器，具有 HFRMREG_LOCAL 的值。</span><span class="sxs-lookup"><span data-stu-id="45594-127">**SelectFormContainer** cannot be used to select the local form container, which has the value HFRMREG_LOCAL.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="45594-128">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="45594-128">MFCMAPI reference</span></span>

<span data-ttu-id="45594-129">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="45594-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="45594-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="45594-130">**File**</span></span>|<span data-ttu-id="45594-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="45594-131">**Function**</span></span>|<span data-ttu-id="45594-132">**Comment**</span><span class="sxs-lookup"><span data-stu-id="45594-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45594-133">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="45594-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="45594-134">CMainDlg::OnSelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="45594-134">CMainDlg::OnSelectFormContainer</span></span>  <br/> |<span data-ttu-id="45594-135">MFCMAPI 使用**IMAPIFormMgr::SelectFormContainer**方法呈现其内容之前选择窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="45594-135">MFCMAPI uses the **IMAPIFormMgr::SelectFormContainer** method to select a form container before rendering its contents.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="45594-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45594-136">See also</span></span>



[<span data-ttu-id="45594-137">IMAPIFormMgr: IUnknown</span><span class="sxs-lookup"><span data-stu-id="45594-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="45594-138">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="45594-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

