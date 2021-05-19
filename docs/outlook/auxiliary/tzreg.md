---
title: TZREG
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a353e1a3-0187-20af-b9ba-43438f6024d5
description: 定义夏令时何时开始、何时返回到标准时间以及夏令时班次的小时数。
ms.openlocfilehash: 136ff6ad0c1a9bc2ad61ef7ba698d66d645165d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419364"
---
# <a name="tzreg"></a><span data-ttu-id="5420b-103">TZREG</span><span class="sxs-lookup"><span data-stu-id="5420b-103">TZREG</span></span>

<span data-ttu-id="5420b-104">定义夏令时何时开始、何时返回到标准时间以及夏令时班次的小时数。</span><span class="sxs-lookup"><span data-stu-id="5420b-104">Defines when daylight saving time starts, when the return to standard time occurs, and how many hours the daylight saving shift is.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5420b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5420b-105">Quick info</span></span>

```cpp
typedef struct RenTimeZone { 
    long        lBias;  
    long        lStandardBias; 
    long        lDaylightBias; 
    SYSTEMTIME  stStandardDate; 
    SYSTEMTIME  stDaylightDate; 
} TZREG; 

```

## <a name="members"></a><span data-ttu-id="5420b-106">成员</span><span class="sxs-lookup"><span data-stu-id="5420b-106">Members</span></span>

<span data-ttu-id="5420b-107">_lBias_</span><span class="sxs-lookup"><span data-stu-id="5420b-107">_lBias_</span></span>
  
> <span data-ttu-id="5420b-108">与格林威治标准时间 (GMT) 。</span><span class="sxs-lookup"><span data-stu-id="5420b-108">The offset from Greenwich Mean Time (GMT).</span></span>
    
<span data-ttu-id="5420b-109">_lStandardBias_</span><span class="sxs-lookup"><span data-stu-id="5420b-109">_lStandardBias_</span></span>
  
> <span data-ttu-id="5420b-110">标准时间与偏置的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5420b-110">The offset from bias during standard time.</span></span>
    
<span data-ttu-id="5420b-111">_lDaylightBias_</span><span class="sxs-lookup"><span data-stu-id="5420b-111">_lDaylightBias_</span></span>
  
> <span data-ttu-id="5420b-112">夏令时期间与偏置的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5420b-112">The offset from bias during daylight saving time.</span></span>
    
<span data-ttu-id="5420b-113">_stStandardDate_</span><span class="sxs-lookup"><span data-stu-id="5420b-113">_stStandardDate_</span></span>
  
> <span data-ttu-id="5420b-114">切换到标准时间的时间。</span><span class="sxs-lookup"><span data-stu-id="5420b-114">The time to switch to standard time.</span></span>
    
<span data-ttu-id="5420b-115">_stDaylightDate_</span><span class="sxs-lookup"><span data-stu-id="5420b-115">_stDaylightDate_</span></span>
  
> <span data-ttu-id="5420b-116">切换到夏令时的时间。</span><span class="sxs-lookup"><span data-stu-id="5420b-116">The time to switch to daylight saving time.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5420b-117">备注</span><span class="sxs-lookup"><span data-stu-id="5420b-117">Remarks</span></span>

<span data-ttu-id="5420b-118">此结构类似于 **TIME_ZONE_INFORMATION**。</span><span class="sxs-lookup"><span data-stu-id="5420b-118">This structure is similar to **TIME_ZONE_INFORMATION**.</span></span> <span data-ttu-id="5420b-119">这是旧客户端用于存储定期会议的时区信息的结构。</span><span class="sxs-lookup"><span data-stu-id="5420b-119">This is the structure used by legacy clients to store time zone information for recurring meetings.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5420b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5420b-120">See also</span></span>

- [<span data-ttu-id="5420b-121">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="5420b-121">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [<span data-ttu-id="5420b-122">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="5420b-122">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)  
- [<span data-ttu-id="5420b-123">TZRULE</span><span class="sxs-lookup"><span data-stu-id="5420b-123">TZRULE</span></span>](tzrule.md)

