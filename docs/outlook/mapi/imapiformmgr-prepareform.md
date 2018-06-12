---
title: IMAPIFormMgrPrepareForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.PrepareForm
api_type:
- COM
ms.assetid: 8f8ee2cb-1c2a-4958-b01e-2f4aab689f89
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3b10ac5906be0f95930be3bef51fe2d78d583b03
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775441"
---
# <a name="imapiformmgrprepareform"></a><span data-ttu-id="37289-103">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="37289-103">IMAPIFormMgr::PrepareForm</span></span>

  
  
<span data-ttu-id="37289-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="37289-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="37289-105">下载用于打开的表单。</span><span class="sxs-lookup"><span data-stu-id="37289-105">Downloads a form for opening.</span></span>
  
```cpp
HRESULT PrepareForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMINFO pfrmiInfo
);
```

## <a name="parameters"></a><span data-ttu-id="37289-106">参数</span><span class="sxs-lookup"><span data-stu-id="37289-106">Parameters</span></span>

 <span data-ttu-id="37289-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="37289-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="37289-108">[in]下载表单时显示进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="37289-108">[in] A handle to the parent window of the progress indicator that is displayed while the form is downloaded.</span></span> <span data-ttu-id="37289-109">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="37289-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="37289-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="37289-110">_ulFlags_</span></span>
  
> <span data-ttu-id="37289-111">[in]位掩码的标志，控制如何下载窗体。</span><span class="sxs-lookup"><span data-stu-id="37289-111">[in] A bitmask of flags that controls how the form is downloaded.</span></span> <span data-ttu-id="37289-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="37289-112">The following flag can be set:</span></span>
    
<span data-ttu-id="37289-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="37289-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="37289-114">显示用户界面，以提供状态或提示用户输入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="37289-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="37289-115">如果未设置此标志，将显示没有用户界面。</span><span class="sxs-lookup"><span data-stu-id="37289-115">If this flag is not set, no user interface is displayed.</span></span>
    
 <span data-ttu-id="37289-116">_pfrmiInfo_</span><span class="sxs-lookup"><span data-stu-id="37289-116">_pfrmiInfo_</span></span>
  
> <span data-ttu-id="37289-117">[in]指向要下载的窗体的窗体信息对象的指针。</span><span class="sxs-lookup"><span data-stu-id="37289-117">[in] A pointer to a form information object for the form to be downloaded.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="37289-118">返回值</span><span class="sxs-lookup"><span data-stu-id="37289-118">Return value</span></span>

<span data-ttu-id="37289-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="37289-119">S_OK</span></span> 
  
> <span data-ttu-id="37289-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="37289-120">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="37289-121">备注</span><span class="sxs-lookup"><span data-stu-id="37289-121">Remarks</span></span>

<span data-ttu-id="37289-122">表单查看器调用**IMAPIFormMgr::PrepareForm**方法从打开的窗体容器下载窗体。</span><span class="sxs-lookup"><span data-stu-id="37289-122">Form viewers call the **IMAPIFormMgr::PrepareForm** method to download a form from a form container for opening.</span></span> <span data-ttu-id="37289-123">大多数表单查看器不需要调用**PrepareForm**，因为[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)和[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法调用**PrepareForm**，如有必要。</span><span class="sxs-lookup"><span data-stu-id="37289-123">Most form viewers do not need to call **PrepareForm**, because both the [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) and [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) methods call **PrepareForm**, if necessary.</span></span> 
  
<span data-ttu-id="37289-124">您可以使用**PrepareForm**获取动态链接库 (Dll) 和修改其表单相关联的其他文件。</span><span class="sxs-lookup"><span data-stu-id="37289-124">You can use **PrepareForm** to obtain the dynamic-link libraries (DLLs) and other files associated with a form to modify them.</span></span> <span data-ttu-id="37289-125">如果回其窗体容器加载修改窗体时，必须重新安装。</span><span class="sxs-lookup"><span data-stu-id="37289-125">If the modified form is loaded back into its form container, it must be reinstalled.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="37289-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37289-126">See also</span></span>



[<span data-ttu-id="37289-127">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="37289-127">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="37289-128">IMAPIFormMgr::LoadForm</span><span class="sxs-lookup"><span data-stu-id="37289-128">IMAPIFormMgr::LoadForm</span></span>](imapiformmgr-loadform.md)
  
[<span data-ttu-id="37289-129">IMAPIFormMgr: IUnknown</span><span class="sxs-lookup"><span data-stu-id="37289-129">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

