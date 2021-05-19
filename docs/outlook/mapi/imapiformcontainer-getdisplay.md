---
title: IMAPIFormContainerGetDisplay
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.GetDisplay
api_type:
- COM
ms.assetid: 6829e273-4a75-4278-b58a-ae7543e075ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 994041d050df56fd3fa3c0e599542e05a202ad65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416130"
---
# <a name="imapiformcontainergetdisplay"></a><span data-ttu-id="757fe-103">IMAPIFormContainer::GetDisplay</span><span class="sxs-lookup"><span data-stu-id="757fe-103">IMAPIFormContainer::GetDisplay</span></span>

  
  
<span data-ttu-id="757fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="757fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="757fe-105">返回显示名称容器的容器。</span><span class="sxs-lookup"><span data-stu-id="757fe-105">Returns the display name of a form container.</span></span>
  
```cpp
HRESULT GetDisplay(
  ULONG ulFlags,
  LPSTR FAR * pszDisplayName
);
```

## <a name="parameters"></a><span data-ttu-id="757fe-106">参数</span><span class="sxs-lookup"><span data-stu-id="757fe-106">Parameters</span></span>

 <span data-ttu-id="757fe-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="757fe-107">_ulFlags_</span></span>
  
> <span data-ttu-id="757fe-108">[in]控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="757fe-108">[in] A bitmask of flags that controls the type of the returned string.</span></span> <span data-ttu-id="757fe-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="757fe-109">The following flag can be set:</span></span>
    
<span data-ttu-id="757fe-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="757fe-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="757fe-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="757fe-111">The returned string is in Unicode format.</span></span> <span data-ttu-id="757fe-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="757fe-112">If the MAPI_UNICODE flag is not set, the string is in ANSI format.</span></span>
    
 <span data-ttu-id="757fe-113">_pszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="757fe-113">_pszDisplayName_</span></span>
  
> <span data-ttu-id="757fe-114">[out]指向包含表单容器显示名称字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="757fe-114">[out] A pointer to a string that contains the display name of the form container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="757fe-115">返回值</span><span class="sxs-lookup"><span data-stu-id="757fe-115">Return value</span></span>

<span data-ttu-id="757fe-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="757fe-116">S_OK</span></span> 
  
> <span data-ttu-id="757fe-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="757fe-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="757fe-118">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="757fe-118">MFCMAPI reference</span></span>

<span data-ttu-id="757fe-119">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="757fe-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="757fe-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="757fe-120">**File**</span></span>|<span data-ttu-id="757fe-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="757fe-121">**Function**</span></span>|<span data-ttu-id="757fe-122">**备注**</span><span class="sxs-lookup"><span data-stu-id="757fe-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="757fe-123">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="757fe-123">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="757fe-124">CFormContainerDlg：：CFormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="757fe-124">CFormContainerDlg::CFormContainerDlg</span></span>  <br/> |<span data-ttu-id="757fe-125">MFCMAPI 在呈现 **CFormContainerDlg 时，使用 IMAPIFormContainer：：GetDisplay** 方法获取表单容器的名称。</span><span class="sxs-lookup"><span data-stu-id="757fe-125">MFCMAPI uses the **IMAPIFormContainer::GetDisplay** method to get the name of the form container when it renders CFormContainerDlg.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="757fe-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="757fe-126">See also</span></span>



[<span data-ttu-id="757fe-127">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="757fe-127">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="757fe-128">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="757fe-128">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

