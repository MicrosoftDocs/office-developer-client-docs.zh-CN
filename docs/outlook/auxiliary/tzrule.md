---
title: TZRULE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75ed353c-7d3e-e148-4057-715e82a0f32c
description: 指定有关夏时制开始时间的时区规则的信息, 以及该时区规则优先的生效年份。
ms.openlocfilehash: 71ede7c0061a058c2dd85c7b9b36c42583a6bb84
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328614"
---
# <a name="tzrule"></a><span data-ttu-id="18e77-103">TZRULE</span><span class="sxs-lookup"><span data-stu-id="18e77-103">TZRULE</span></span>

<span data-ttu-id="18e77-104">指定有关夏时制开始时间的时区规则的信息, 以及该时区规则优先的生效年份。</span><span class="sxs-lookup"><span data-stu-id="18e77-104">Specifies information for a time zone rule about when daylight saving time starts, and the year in which that time zone rule first takes effect.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="18e77-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="18e77-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD        wFlags;  
    SYSTEMTIME  stStart; 
    TZREG       TZReg; 
} TZRULE;
```

## <a name="members"></a><span data-ttu-id="18e77-106">成员</span><span class="sxs-lookup"><span data-stu-id="18e77-106">Members</span></span>

<span data-ttu-id="18e77-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="18e77-107">_wFlags_</span></span>
  
> <span data-ttu-id="18e77-108">为此成员设置的标志标识了此时区规则的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="18e77-108">The flags set for this member identify specific details for this time zone rule.</span></span> <span data-ttu-id="18e77-109">可能的标志如下所示:</span><span class="sxs-lookup"><span data-stu-id="18e77-109">The possible flags are as follows:</span></span>
    
   - <span data-ttu-id="18e77-110">**TZRULE_FLAG_EFFECTIVE_TZREG** —将规则标识为当前应使用的规则。</span><span class="sxs-lookup"><span data-stu-id="18e77-110">**TZRULE_FLAG_EFFECTIVE_TZREG** —Identifies the rule as the one that should be used currently.</span></span> <span data-ttu-id="18e77-111">只能将一个规则标记为有效规则。</span><span class="sxs-lookup"><span data-stu-id="18e77-111">Only one rule can be marked as the effective rule.</span></span> <span data-ttu-id="18e77-112">所有其他规则仅用于比较目的。</span><span class="sxs-lookup"><span data-stu-id="18e77-112">All other rules are for comparison purposes only.</span></span> 
    
   - <span data-ttu-id="18e77-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** —在定期会议中, 标识与[PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)中的规则匹配的规则。</span><span class="sxs-lookup"><span data-stu-id="18e77-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** —On recurring meetings, identifies the rule as matching the rule in [PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx).</span></span> <span data-ttu-id="18e77-114">这可用于检测**PidLidTimeZoneStruct**是否已由旧版客户端显著修改, 这将在其他方面不知道新的、更完整的属性。</span><span class="sxs-lookup"><span data-stu-id="18e77-114">This can be used to detect whether **PidLidTimeZoneStruct** has been modified significantly by a legacy client, which would be otherwise unaware of the new, more complete property.</span></span> 
    
<span data-ttu-id="18e77-115">_stStart_</span><span class="sxs-lookup"><span data-stu-id="18e77-115">_stStart_</span></span>
  
> <span data-ttu-id="18e77-116">时区规则启动的协调世界时 (UTC) 时间。</span><span class="sxs-lookup"><span data-stu-id="18e77-116">The time in Coordinated Universal Time (UTC) that the time zone rule started.</span></span>
    
<span data-ttu-id="18e77-117">_TZReg_</span><span class="sxs-lookup"><span data-stu-id="18e77-117">_TZReg_</span></span>
  
> <span data-ttu-id="18e77-118">时区规则的时区信息。</span><span class="sxs-lookup"><span data-stu-id="18e77-118">The time zone information for the time zone rule.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="18e77-119">注解</span><span class="sxs-lookup"><span data-stu-id="18e77-119">Remarks</span></span>

<span data-ttu-id="18e77-120">此结构通过提供其他信息来扩充[TZREG](tzreg.md) , 以指示时区规则何时生效。</span><span class="sxs-lookup"><span data-stu-id="18e77-120">This structure augments [TZREG](tzreg.md) by providing additional information indicating when time zone rules take effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18e77-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18e77-121">See also</span></span>

- [<span data-ttu-id="18e77-122">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="18e77-122">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) 
- [<span data-ttu-id="18e77-123">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="18e77-123">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="18e77-124">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="18e77-124">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
- [<span data-ttu-id="18e77-125">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="18e77-125">TZDEFINITION</span></span>](tzdefinition.md)

