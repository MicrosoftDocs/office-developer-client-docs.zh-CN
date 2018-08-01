---
title: IOlkApptRebaserEndRebaseAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e47d5a8d-6a13-f430-fbfd-00df04b4a006
description: 等待约会重定基址来完成，并检索结果。
ms.openlocfilehash: fd27021ce05b1d5b95fd258e0ee89b5bd4f2c7db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774369"
---
# <a name="iolkapptrebaserendrebaseappointments"></a><span data-ttu-id="265b7-103">IOlkApptRebaser::EndRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="265b7-103">IOlkApptRebaser::EndRebaseAppointments</span></span>

<span data-ttu-id="265b7-104">等待约会重定基址来完成，并检索结果。</span><span class="sxs-lookup"><span data-stu-id="265b7-104">Waits for appointment rebasing to complete and retrieves the results.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="265b7-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="265b7-105">Quick info</span></span>

<span data-ttu-id="265b7-106">请参阅[IOlkApptRebaser](iolkapptrebaser.md)。</span><span class="sxs-lookup"><span data-stu-id="265b7-106">See [IOlkApptRebaser](iolkapptrebaser.md).</span></span>
  
```cpp
HRESULT EndRebaseAppointments( 
    void *pContext, 
    HRESULT *phResult);
```

## <a name="parameters"></a><span data-ttu-id="265b7-107">参数</span><span class="sxs-lookup"><span data-stu-id="265b7-107">Parameters</span></span>

<span data-ttu-id="265b7-108">_pContext_</span><span class="sxs-lookup"><span data-stu-id="265b7-108">_pContext_</span></span>
  
> <span data-ttu-id="265b7-p101">[中]所必需。指向来自对[IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)的调用上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="265b7-p101">[in] Required. A pointer to the context obtained from a call to [IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md).</span></span>
    
<span data-ttu-id="265b7-111">_phResult_</span><span class="sxs-lookup"><span data-stu-id="265b7-111">_phResult_</span></span>
  
> <span data-ttu-id="265b7-p102">[] out所必需。一个指向的 **HRESULT** 以检索重定基址操作的结果。</span><span class="sxs-lookup"><span data-stu-id="265b7-p102">[out] Required. A pointer to an **HRESULT** to retrieve the result of the rebasing operation.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="265b7-114">返回值</span><span class="sxs-lookup"><span data-stu-id="265b7-114">Return values</span></span>

<span data-ttu-id="265b7-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="265b7-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="265b7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="265b7-116">See also</span></span>

- [<span data-ttu-id="265b7-117">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="265b7-117">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

