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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ace31079c51aac169f6091af0cb363e7f05f0d14
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427736"
---
# <a name="mapiopenlocalformcontainer"></a><span data-ttu-id="1ae42-103">MAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="1ae42-103">MAPIOpenLocalFormContainer</span></span>

  
  
<span data-ttu-id="1ae42-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ae42-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ae42-105">返回指向本地表单库的接口指针。</span><span class="sxs-lookup"><span data-stu-id="1ae42-105">Returns an interface pointer to the local form library.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1ae42-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1ae42-106">Header file:</span></span>  <br/> |<span data-ttu-id="1ae42-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="1ae42-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="1ae42-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="1ae42-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1ae42-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1ae42-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1ae42-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="1ae42-110">Called by:</span></span>  <br/> |<span data-ttu-id="1ae42-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1ae42-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenLocalFormContainer(
  LPMAPIFORMCONTAINER FAR * ppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="1ae42-112">参数</span><span class="sxs-lookup"><span data-stu-id="1ae42-112">Parameters</span></span>

 <span data-ttu-id="1ae42-113">_ppfcnt_</span><span class="sxs-lookup"><span data-stu-id="1ae42-113">_ppfcnt_</span></span>
  
> <span data-ttu-id="1ae42-114">[out]指向指向本地表单库接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1ae42-114">[out] Pointer to a pointer to the local form library interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1ae42-115">返回值</span><span class="sxs-lookup"><span data-stu-id="1ae42-115">Return value</span></span>

<span data-ttu-id="1ae42-116">无。</span><span class="sxs-lookup"><span data-stu-id="1ae42-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1ae42-117">说明</span><span class="sxs-lookup"><span data-stu-id="1ae42-117">Remarks</span></span>

<span data-ttu-id="1ae42-118">第三方安装程序可以使用返回指针的接口将特定于应用程序的表单安装到库中，而程序无需首先登录 MAPI。</span><span class="sxs-lookup"><span data-stu-id="1ae42-118">The interface to which a pointer is returned can be used by third-party installation programs to install application-specific forms into the library without the program first having to log on to MAPI.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1ae42-119">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="1ae42-119">MFCMAPI reference</span></span>

<span data-ttu-id="1ae42-120">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1ae42-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1ae42-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="1ae42-121">**File**</span></span>|<span data-ttu-id="1ae42-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="1ae42-122">**Function**</span></span>|<span data-ttu-id="1ae42-123">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ae42-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ae42-124">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="1ae42-124">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="1ae42-125">CMainDlg：：OnMAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="1ae42-125">CMainDlg::OnMAPIOpenLocalFormContainer</span></span>  <br/> |<span data-ttu-id="1ae42-126">MFCMAPI 使用 **MAPIOpenLocalFormContainer** 方法打开本地表单容器以在新窗口中呈现。</span><span class="sxs-lookup"><span data-stu-id="1ae42-126">MFCMAPI uses the **MAPIOpenLocalFormContainer** method to open the local form container to render in a new window.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1ae42-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ae42-127">See also</span></span>



[<span data-ttu-id="1ae42-128">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1ae42-128">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

