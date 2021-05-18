---
title: TZRULE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75ed353c-7d3e-e148-4057-715e82a0f32c
description: 指定有关夏令时何时开始以及该时区规则首先生效的年份的时区规则的信息。
ms.openlocfilehash: 71ede7c0061a058c2dd85c7b9b36c42583a6bb84
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328614"
---
# <a name="tzrule"></a><span data-ttu-id="04336-103">TZRULE</span><span class="sxs-lookup"><span data-stu-id="04336-103">TZRULE</span></span>

<span data-ttu-id="04336-104">指定有关夏令时何时开始以及该时区规则首先生效的年份的时区规则的信息。</span><span class="sxs-lookup"><span data-stu-id="04336-104">Specifies information for a time zone rule about when daylight saving time starts, and the year in which that time zone rule first takes effect.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="04336-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="04336-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD        wFlags;  
    SYSTEMTIME  stStart; 
    TZREG       TZReg; 
} TZRULE;
```

## <a name="members"></a><span data-ttu-id="04336-106">成员</span><span class="sxs-lookup"><span data-stu-id="04336-106">Members</span></span>

<span data-ttu-id="04336-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="04336-107">_wFlags_</span></span>
  
> <span data-ttu-id="04336-108">为此成员设置的标志标识此时区规则的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="04336-108">The flags set for this member identify specific details for this time zone rule.</span></span> <span data-ttu-id="04336-109">可能的标志如下所示：</span><span class="sxs-lookup"><span data-stu-id="04336-109">The possible flags are as follows:</span></span>
    
   - <span data-ttu-id="04336-110">**TZRULE_FLAG_EFFECTIVE_TZREG** — 将规则标识为当前应该使用的规则。</span><span class="sxs-lookup"><span data-stu-id="04336-110">**TZRULE_FLAG_EFFECTIVE_TZREG** —Identifies the rule as the one that should be used currently.</span></span> <span data-ttu-id="04336-111">只能将一个规则标记为有效规则。</span><span class="sxs-lookup"><span data-stu-id="04336-111">Only one rule can be marked as the effective rule.</span></span> <span data-ttu-id="04336-112">所有其他规则仅供比较。</span><span class="sxs-lookup"><span data-stu-id="04336-112">All other rules are for comparison purposes only.</span></span> 
    
   - <span data-ttu-id="04336-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** - 在定期会议中，将规则标识为 [与 PidLidTimeZoneStruct 中的规则匹配](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="04336-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** —On recurring meetings, identifies the rule as matching the rule in [PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx).</span></span> <span data-ttu-id="04336-114">这可用于检测旧客户端是否已对 **PidLidTimeZoneStruct** 进行了重大修改，否则，不会知道新的、更完整的属性。</span><span class="sxs-lookup"><span data-stu-id="04336-114">This can be used to detect whether **PidLidTimeZoneStruct** has been modified significantly by a legacy client, which would be otherwise unaware of the new, more complete property.</span></span> 
    
<span data-ttu-id="04336-115">_stStart_</span><span class="sxs-lookup"><span data-stu-id="04336-115">_stStart_</span></span>
  
> <span data-ttu-id="04336-116">以协调世界时 (UTC) 时区规则开始的时间。</span><span class="sxs-lookup"><span data-stu-id="04336-116">The time in Coordinated Universal Time (UTC) that the time zone rule started.</span></span>
    
<span data-ttu-id="04336-117">_TZReg_</span><span class="sxs-lookup"><span data-stu-id="04336-117">_TZReg_</span></span>
  
> <span data-ttu-id="04336-118">时区规则的时区信息。</span><span class="sxs-lookup"><span data-stu-id="04336-118">The time zone information for the time zone rule.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="04336-119">备注</span><span class="sxs-lookup"><span data-stu-id="04336-119">Remarks</span></span>

<span data-ttu-id="04336-120">此结构通过提供指示时区规则何时生效的其他信息来扩充[TZREG。](tzreg.md)</span><span class="sxs-lookup"><span data-stu-id="04336-120">This structure augments [TZREG](tzreg.md) by providing additional information indicating when time zone rules take effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="04336-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04336-121">See also</span></span>

- [<span data-ttu-id="04336-122">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="04336-122">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) 
- [<span data-ttu-id="04336-123">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="04336-123">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="04336-124">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="04336-124">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
- [<span data-ttu-id="04336-125">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="04336-125">TZDEFINITION</span></span>](tzdefinition.md)

