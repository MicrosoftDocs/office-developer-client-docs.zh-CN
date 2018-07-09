---
title: MAPIOpenLocalFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenLocalFormContainer
api_type:
- COM
ms.assetid: 1c53170f-03a6-4a05-913e-de8eeadea692
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c00c2fa04ae7e89f8c23c085ba021a935748ad4e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776392"
---
# <a name="mapiopenlocalformcontainer"></a><span data-ttu-id="f3d6b-103">MAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3d6b-103">MAPIOpenLocalFormContainer</span></span>

  
  
<span data-ttu-id="f3d6b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f3d6b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f3d6b-105">返回到本地表单库的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-105">Returns an interface pointer to the local form library.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3d6b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f3d6b-106">Header file:</span></span>  <br/> |<span data-ttu-id="f3d6b-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="f3d6b-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="f3d6b-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f3d6b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f3d6b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f3d6b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f3d6b-110">调用：</span><span class="sxs-lookup"><span data-stu-id="f3d6b-110">Called by:</span></span>  <br/> |<span data-ttu-id="f3d6b-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="f3d6b-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenLocalFormContainer(
  LPMAPIFORMCONTAINER FAR * ppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="f3d6b-112">参数</span><span class="sxs-lookup"><span data-stu-id="f3d6b-112">Parameters</span></span>

 <span data-ttu-id="f3d6b-113">_ppfcnt_</span><span class="sxs-lookup"><span data-stu-id="f3d6b-113">_ppfcnt_</span></span>
  
> <span data-ttu-id="f3d6b-114">[输出]指向本地窗体库接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-114">[out] Pointer to a pointer to the local form library interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f3d6b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f3d6b-115">Return value</span></span>

<span data-ttu-id="f3d6b-116">无。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f3d6b-117">备注</span><span class="sxs-lookup"><span data-stu-id="f3d6b-117">Remarks</span></span>

<span data-ttu-id="f3d6b-118">第三方安装程序可以使用指针返回到该接口到库中安装应用程序特定的表单，而无需程序事先登录到 MAPI。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-118">The interface to which a pointer is returned can be used by third-party installation programs to install application-specific forms into the library without the program first having to log on to MAPI.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f3d6b-119">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="f3d6b-119">MFCMAPI reference</span></span>

<span data-ttu-id="f3d6b-120">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f3d6b-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="f3d6b-121">**File**</span></span>|<span data-ttu-id="f3d6b-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="f3d6b-122">**Function**</span></span>|<span data-ttu-id="f3d6b-123">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f3d6b-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3d6b-124">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="f3d6b-124">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="f3d6b-125">CMainDlg::OnMAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3d6b-125">CMainDlg::OnMAPIOpenLocalFormContainer</span></span>  <br/> |<span data-ttu-id="f3d6b-126">MFCMAPI 使用**MAPIOpenLocalFormContainer**方法打开要在新窗口中呈现的本地窗体容器。</span><span class="sxs-lookup"><span data-stu-id="f3d6b-126">MFCMAPI uses the **MAPIOpenLocalFormContainer** method to open the local form container to render in a new window.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f3d6b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3d6b-127">See also</span></span>



[<span data-ttu-id="f3d6b-128">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="f3d6b-128">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

