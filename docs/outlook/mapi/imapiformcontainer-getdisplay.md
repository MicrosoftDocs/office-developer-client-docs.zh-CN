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
ms.openlocfilehash: 66e23d73af53b05295bf2cbcd8c604ab3545bbca
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573136"
---
# <a name="imapiformcontainergetdisplay"></a><span data-ttu-id="6e07d-103">IMAPIFormContainer::GetDisplay</span><span class="sxs-lookup"><span data-stu-id="6e07d-103">IMAPIFormContainer::GetDisplay</span></span>

  
  
<span data-ttu-id="6e07d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e07d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e07d-105">返回一个窗体容器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="6e07d-105">Returns the display name of a form container.</span></span>
  
```cpp
HRESULT GetDisplay(
  ULONG ulFlags,
  LPSTR FAR * pszDisplayName
);
```

## <a name="parameters"></a><span data-ttu-id="6e07d-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e07d-106">Parameters</span></span>

 <span data-ttu-id="6e07d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6e07d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6e07d-108">[in]位掩码的标志的控制返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="6e07d-108">[in] A bitmask of flags that controls the type of the returned string.</span></span> <span data-ttu-id="6e07d-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="6e07d-109">The following flag can be set:</span></span>
    
<span data-ttu-id="6e07d-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6e07d-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6e07d-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6e07d-111">The returned string is in Unicode format.</span></span> <span data-ttu-id="6e07d-112">如果未设置 MAPI_UNICODE 标志，该字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6e07d-112">If the MAPI_UNICODE flag is not set, the string is in ANSI format.</span></span>
    
 <span data-ttu-id="6e07d-113">_pszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="6e07d-113">_pszDisplayName_</span></span>
  
> <span data-ttu-id="6e07d-114">[输出]一个指向包含窗体容器的显示名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="6e07d-114">[out] A pointer to a string that contains the display name of the form container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6e07d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="6e07d-115">Return value</span></span>

<span data-ttu-id="6e07d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e07d-116">S_OK</span></span> 
  
> <span data-ttu-id="6e07d-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="6e07d-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="6e07d-118">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="6e07d-118">MFCMAPI reference</span></span>

<span data-ttu-id="6e07d-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6e07d-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6e07d-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="6e07d-120">**File**</span></span>|<span data-ttu-id="6e07d-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="6e07d-121">**Function**</span></span>|<span data-ttu-id="6e07d-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="6e07d-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e07d-123">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="6e07d-123">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="6e07d-124">CFormContainerDlg::CFormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="6e07d-124">CFormContainerDlg::CFormContainerDlg</span></span>  <br/> |<span data-ttu-id="6e07d-125">MFCMAPI 使用**IMAPIFormContainer::GetDisplay**方法来呈现 CFormContainerDlg 时获取窗体容器的名称。</span><span class="sxs-lookup"><span data-stu-id="6e07d-125">MFCMAPI uses the **IMAPIFormContainer::GetDisplay** method to get the name of the form container when it renders CFormContainerDlg.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6e07d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e07d-126">See also</span></span>



[<span data-ttu-id="6e07d-127">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e07d-127">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="6e07d-128">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6e07d-128">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

