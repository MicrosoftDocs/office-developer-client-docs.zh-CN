---
title: TZRULE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75ed353c-7d3e-e148-4057-715e82a0f32c
description: 指定的时区规则时夏时制开始，以及该所在的时区规则首先会生效的年份的信息。
ms.openlocfilehash: 71ede7c0061a058c2dd85c7b9b36c42583a6bb84
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392695"
---
# <a name="tzrule"></a><span data-ttu-id="5527f-103">TZRULE</span><span class="sxs-lookup"><span data-stu-id="5527f-103">TZRULE</span></span>

<span data-ttu-id="5527f-104">指定的时区规则时夏时制开始，以及该所在的时区规则首先会生效的年份的信息。</span><span class="sxs-lookup"><span data-stu-id="5527f-104">Specifies information for a time zone rule about when daylight saving time starts, and the year in which that time zone rule first takes effect.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="5527f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5527f-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD        wFlags;  
    SYSTEMTIME  stStart; 
    TZREG       TZReg; 
} TZRULE;
```

## <a name="members"></a><span data-ttu-id="5527f-106">Members</span><span class="sxs-lookup"><span data-stu-id="5527f-106">Members</span></span>

<span data-ttu-id="5527f-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="5527f-107">_wFlags_</span></span>
  
> <span data-ttu-id="5527f-108">为此成员的标志确定具体的详细信息，此所在的时区规则。</span><span class="sxs-lookup"><span data-stu-id="5527f-108">The flags set for this member identify specific details for this time zone rule.</span></span> <span data-ttu-id="5527f-109">可能的标志如下所示：</span><span class="sxs-lookup"><span data-stu-id="5527f-109">The possible flags are as follows:</span></span>
    
   - <span data-ttu-id="5527f-110">**TZRULE_FLAG_EFFECTIVE_TZREG** — 标识为，应当前使用的规则。</span><span class="sxs-lookup"><span data-stu-id="5527f-110">**TZRULE_FLAG_EFFECTIVE_TZREG** —Identifies the rule as the one that should be used currently.</span></span> <span data-ttu-id="5527f-111">只有一个规则可以标记为有效的规则。</span><span class="sxs-lookup"><span data-stu-id="5527f-111">Only one rule can be marked as the effective rule.</span></span> <span data-ttu-id="5527f-112">所有其他规则只是为了比较。</span><span class="sxs-lookup"><span data-stu-id="5527f-112">All other rules are for comparison purposes only.</span></span> 
    
   - <span data-ttu-id="5527f-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** — 在定期会议标识为匹配[PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)中的规则的规则。</span><span class="sxs-lookup"><span data-stu-id="5527f-113">**TZRULE_FLAG_RECUR_CURRENT_TZREG** —On recurring meetings, identifies the rule as matching the rule in [PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx).</span></span> <span data-ttu-id="5527f-114">这可以用于检测是否**PidLidTimeZoneStruct**已修改显著旧客户端，否则不知道的新的、 更完整属性将为。</span><span class="sxs-lookup"><span data-stu-id="5527f-114">This can be used to detect whether **PidLidTimeZoneStruct** has been modified significantly by a legacy client, which would be otherwise unaware of the new, more complete property.</span></span> 
    
<span data-ttu-id="5527f-115">_stStart_</span><span class="sxs-lookup"><span data-stu-id="5527f-115">_stStart_</span></span>
  
> <span data-ttu-id="5527f-116">以协调世界时 (UTC) 时区规则启动的时间。</span><span class="sxs-lookup"><span data-stu-id="5527f-116">The time in Coordinated Universal Time (UTC) that the time zone rule started.</span></span>
    
<span data-ttu-id="5527f-117">_TZReg_</span><span class="sxs-lookup"><span data-stu-id="5527f-117">_TZReg_</span></span>
  
> <span data-ttu-id="5527f-118">所在的时区规则的时区信息。</span><span class="sxs-lookup"><span data-stu-id="5527f-118">The time zone information for the time zone rule.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5527f-119">说明</span><span class="sxs-lookup"><span data-stu-id="5527f-119">Remarks</span></span>

<span data-ttu-id="5527f-120">此结构补充[TZREG](tzreg.md)提供了指示时所在的时区规则才会生效的其他信息。</span><span class="sxs-lookup"><span data-stu-id="5527f-120">This structure augments [TZREG](tzreg.md) by providing additional information indicating when time zone rules take effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5527f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5527f-121">See also</span></span>

- [<span data-ttu-id="5527f-122">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="5527f-122">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) 
- [<span data-ttu-id="5527f-123">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="5527f-123">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="5527f-124">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="5527f-124">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
- [<span data-ttu-id="5527f-125">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="5527f-125">TZDEFINITION</span></span>](tzdefinition.md)

