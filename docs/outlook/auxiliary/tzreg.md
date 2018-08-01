---
title: TZREG
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a353e1a3-0187-20af-b9ba-43438f6024d5
description: 定义夏时制时间启动时，返回到标准时间发生时，和多少个小时夏 shift 是。
ms.openlocfilehash: 85812ab053d77c07f9360b6bf3a1faaf72cae573
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774463"
---
# <a name="tzreg"></a><span data-ttu-id="d4400-103">TZREG</span><span class="sxs-lookup"><span data-stu-id="d4400-103">TZREG</span></span>

<span data-ttu-id="d4400-104">定义夏时制时间启动时，返回到标准时间发生时，和多少个小时夏 shift 是。</span><span class="sxs-lookup"><span data-stu-id="d4400-104">Defines when daylight saving time starts, when the return to standard time occurs, and how many hours the daylight saving shift is.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d4400-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d4400-105">Quick info</span></span>

```cpp
typedef struct RenTimeZone { 
    long        lBias;  
    long        lStandardBias; 
    long        lDaylightBias; 
    SYSTEMTIME  stStandardDate; 
    SYSTEMTIME  stDaylightDate; 
} TZREG; 

```

## <a name="members"></a><span data-ttu-id="d4400-106">Members</span><span class="sxs-lookup"><span data-stu-id="d4400-106">Members</span></span>

<span data-ttu-id="d4400-107">_lBias_</span><span class="sxs-lookup"><span data-stu-id="d4400-107">_lBias_</span></span>
  
> <span data-ttu-id="d4400-108">从格林威治标准时间 (GMT) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="d4400-108">The offset from Greenwich Mean Time (GMT).</span></span>
    
<span data-ttu-id="d4400-109">_lStandardBias_</span><span class="sxs-lookup"><span data-stu-id="d4400-109">_lStandardBias_</span></span>
  
> <span data-ttu-id="d4400-110">从标准时间的偏向的偏移量。</span><span class="sxs-lookup"><span data-stu-id="d4400-110">The offset from bias during standard time.</span></span>
    
<span data-ttu-id="d4400-111">_lDaylightBias_</span><span class="sxs-lookup"><span data-stu-id="d4400-111">_lDaylightBias_</span></span>
  
> <span data-ttu-id="d4400-112">从偏向期间夏时制的偏移量。</span><span class="sxs-lookup"><span data-stu-id="d4400-112">The offset from bias during daylight saving time.</span></span>
    
<span data-ttu-id="d4400-113">_stStandardDate_</span><span class="sxs-lookup"><span data-stu-id="d4400-113">_stStandardDate_</span></span>
  
> <span data-ttu-id="d4400-114">要切换到标准时间的时间。</span><span class="sxs-lookup"><span data-stu-id="d4400-114">The time to switch to standard time.</span></span>
    
<span data-ttu-id="d4400-115">_stDaylightDate_</span><span class="sxs-lookup"><span data-stu-id="d4400-115">_stDaylightDate_</span></span>
  
> <span data-ttu-id="d4400-116">要切换到夏时制的时间。</span><span class="sxs-lookup"><span data-stu-id="d4400-116">The time to switch to daylight saving time.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d4400-117">说明</span><span class="sxs-lookup"><span data-stu-id="d4400-117">Remarks</span></span>

<span data-ttu-id="d4400-118">类似于**TIME_ZONE_INFORMATION**此结构。</span><span class="sxs-lookup"><span data-stu-id="d4400-118">This structure is similar to **TIME_ZONE_INFORMATION**.</span></span> <span data-ttu-id="d4400-119">这是旧客户端用于存储所在的时区定期会议信息的结构。</span><span class="sxs-lookup"><span data-stu-id="d4400-119">This is the structure used by legacy clients to store time zone information for recurring meetings.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4400-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4400-120">See also</span></span>

- [<span data-ttu-id="d4400-121">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="d4400-121">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [<span data-ttu-id="d4400-122">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="d4400-122">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)  
- [<span data-ttu-id="d4400-123">TZRULE</span><span class="sxs-lookup"><span data-stu-id="d4400-123">TZRULE</span></span>](tzrule.md)

