---
title: IOlkApptRebaserEndEnumerateAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bc4506c7-7a4f-940d-d0a6-e0fab4561a88
description: 等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。
ms.openlocfilehash: 5be6fd9ce33374725b36429cd0fbc717776c9ab9
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392016"
---
# <a name="iolkapptrebaserendenumerateappointments"></a><span data-ttu-id="fa441-103">IOlkApptRebaser::EndEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="fa441-103">IOlkApptRebaser::EndEnumerateAppointments</span></span>

<span data-ttu-id="fa441-104">等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。</span><span class="sxs-lookup"><span data-stu-id="fa441-104">Waits for appointment enumeration in a calendar folder to complete and returns a list of appointments that need rebasing.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fa441-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="fa441-105">Quick info</span></span>

<span data-ttu-id="fa441-106">请参阅[IOlkApptRebaser](iolkapptrebaser.md)。</span><span class="sxs-lookup"><span data-stu-id="fa441-106">See [IOlkApptRebaser](iolkapptrebaser.md).</span></span>
  
```cpp
HRESULT EndEnumerateAppointments( 
    void *pContext, 
    HRESULT *phResult, 
    MAPIERROR **ppError, 
    SRowSet **ppRows);
```

## <a name="parameters"></a><span data-ttu-id="fa441-107">参数</span><span class="sxs-lookup"><span data-stu-id="fa441-107">Parameters</span></span>

<span data-ttu-id="fa441-108">_pContext_</span><span class="sxs-lookup"><span data-stu-id="fa441-108">_pContext_</span></span>
  
> <span data-ttu-id="fa441-p101">[中]所必需。指向从以前调用[IOlkApptRebaser::BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)获得的上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="fa441-p101">[in] Required. A pointer to the context obtained from a prior call to [IOlkApptRebaser::BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md).</span></span>
    
<span data-ttu-id="fa441-111">_phResult_</span><span class="sxs-lookup"><span data-stu-id="fa441-111">_phResult_</span></span>
  
> <span data-ttu-id="fa441-p102">[] out所必需。一个指向的 **HRESULT** 以检索枚举操作的结果。</span><span class="sxs-lookup"><span data-stu-id="fa441-p102">[out] Required. A pointer to an **HRESULT** to retrieve the results of the enumeration operation.</span></span> 
    
<span data-ttu-id="fa441-114">_ppError_</span><span class="sxs-lookup"><span data-stu-id="fa441-114">_ppError_</span></span>
  
> <span data-ttu-id="fa441-p103">[] out可选。指向检索扩展的错误信息的 **MAPIERROR** 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fa441-p103">[out] Optional. A pointer to a pointer to a **MAPIERROR** structure to retrieve extended error information.</span></span> 
    
<span data-ttu-id="fa441-117">_ppRows_</span><span class="sxs-lookup"><span data-stu-id="fa441-117">_ppRows_</span></span>
  
> <span data-ttu-id="fa441-p104">[] out所必需。指向描述需要重定基址的约会[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)结构的指针的指针。这种结构通常将传递给[IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)。</span><span class="sxs-lookup"><span data-stu-id="fa441-p104">[out] Required. A pointer to a pointer to an [SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx) structure that describes the appointments that need rebasing. This structure will usually be passed to [IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="fa441-121">返回值</span><span class="sxs-lookup"><span data-stu-id="fa441-121">Return values</span></span>

<span data-ttu-id="fa441-122">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="fa441-122">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa441-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa441-123">See also</span></span>

- [<span data-ttu-id="fa441-124">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="fa441-124">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

