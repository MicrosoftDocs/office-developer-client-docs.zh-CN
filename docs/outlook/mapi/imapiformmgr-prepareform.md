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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0d5d8fe13a3c192dc0b0a8ddc0f5f945fa16f15
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416648"
---
# <a name="imapiformmgrprepareform"></a><span data-ttu-id="150d5-103">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="150d5-103">IMAPIFormMgr::PrepareForm</span></span>

  
  
<span data-ttu-id="150d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="150d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="150d5-105">下载要打开的表单。</span><span class="sxs-lookup"><span data-stu-id="150d5-105">Downloads a form for opening.</span></span>
  
```cpp
HRESULT PrepareForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMINFO pfrmiInfo
);
```

## <a name="parameters"></a><span data-ttu-id="150d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="150d5-106">Parameters</span></span>

 <span data-ttu-id="150d5-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="150d5-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="150d5-108">[in]下载表单时显示的进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="150d5-108">[in] A handle to the parent window of the progress indicator that is displayed while the form is downloaded.</span></span> <span data-ttu-id="150d5-109">除非  _在 ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="150d5-109">The  _ulUIParam_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="150d5-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="150d5-110">_ulFlags_</span></span>
  
> <span data-ttu-id="150d5-111">[in]控制表单下载方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="150d5-111">[in] A bitmask of flags that controls how the form is downloaded.</span></span> <span data-ttu-id="150d5-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="150d5-112">The following flag can be set:</span></span>
    
<span data-ttu-id="150d5-113">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="150d5-113">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="150d5-114">显示用户界面以提供状态或提示用户输入详细信息。</span><span class="sxs-lookup"><span data-stu-id="150d5-114">Displays a user interface to provide status or prompt the user for more information.</span></span> <span data-ttu-id="150d5-115">如果未设置此标志，则不显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="150d5-115">If this flag is not set, no user interface is displayed.</span></span>
    
 <span data-ttu-id="150d5-116">_pfrmiInfo_</span><span class="sxs-lookup"><span data-stu-id="150d5-116">_pfrmiInfo_</span></span>
  
> <span data-ttu-id="150d5-117">[in]指向要下载的表单的表单信息对象的指针。</span><span class="sxs-lookup"><span data-stu-id="150d5-117">[in] A pointer to a form information object for the form to be downloaded.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="150d5-118">返回值</span><span class="sxs-lookup"><span data-stu-id="150d5-118">Return value</span></span>

<span data-ttu-id="150d5-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="150d5-119">S_OK</span></span> 
  
> <span data-ttu-id="150d5-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="150d5-120">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="150d5-121">备注</span><span class="sxs-lookup"><span data-stu-id="150d5-121">Remarks</span></span>

<span data-ttu-id="150d5-122">表单查看器调用 **IMAPIFormMgr：:P repareForm** 方法，从表单容器下载表单以打开。</span><span class="sxs-lookup"><span data-stu-id="150d5-122">Form viewers call the **IMAPIFormMgr::PrepareForm** method to download a form from a form container for opening.</span></span> <span data-ttu-id="150d5-123">大多数表单查看器不需要调用 **PrepareForm，** 因为 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 和 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 方法都调用 **PrepareForm（** 如有必要）。</span><span class="sxs-lookup"><span data-stu-id="150d5-123">Most form viewers do not need to call **PrepareForm**, because both the [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) and [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) methods call **PrepareForm**, if necessary.</span></span> 
  
<span data-ttu-id="150d5-124">可以使用 **PrepareForm** 获取 DLL 中的动态链接库 (DLL) 与表单关联的其他文件来修改它们。</span><span class="sxs-lookup"><span data-stu-id="150d5-124">You can use **PrepareForm** to obtain the dynamic-link libraries (DLLs) and other files associated with a form to modify them.</span></span> <span data-ttu-id="150d5-125">如果修改后的表单加载回其表单容器，则必须重新安装该表单。</span><span class="sxs-lookup"><span data-stu-id="150d5-125">If the modified form is loaded back into its form container, it must be reinstalled.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="150d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="150d5-126">See also</span></span>



[<span data-ttu-id="150d5-127">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="150d5-127">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="150d5-128">IMAPIFormMgr::LoadForm</span><span class="sxs-lookup"><span data-stu-id="150d5-128">IMAPIFormMgr::LoadForm</span></span>](imapiformmgr-loadform.md)
  
[<span data-ttu-id="150d5-129">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="150d5-129">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

