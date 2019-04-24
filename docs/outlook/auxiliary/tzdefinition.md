---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 表示包含所有历史、当前和未来时区班次规则的时区的完整时区 (夏时制)。
ms.openlocfilehash: 5f7000ecc1fa602b330670c2ee1c39f673a11a65
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328292"
---
# <a name="tzdefinition"></a><span data-ttu-id="5b11d-103">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="5b11d-103">TZDEFINITION</span></span>

<span data-ttu-id="5b11d-104">表示包含所有历史、当前和未来时区班次规则的时区的完整时区 (夏时制)。</span><span class="sxs-lookup"><span data-stu-id="5b11d-104">Represents an entire time zone including all historical, current, and future time zone shift rules for daylight saving time.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5b11d-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5b11d-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD     wFlags;  
    LPWSTR   pwszKeyName; 
    WORD     cRules; 
    TZRULE*  rgRules; 
} TZDEFINITION;
```

## <a name="members"></a><span data-ttu-id="5b11d-106">成员</span><span class="sxs-lookup"><span data-stu-id="5b11d-106">Members</span></span>

<span data-ttu-id="5b11d-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="5b11d-107">_wFlags_</span></span>
  
> <span data-ttu-id="5b11d-108">指示表示 Windows 注册表中的时区的键名称有效。</span><span class="sxs-lookup"><span data-stu-id="5b11d-108">Indicates that the key name that represents the time zone in the Windows registry is valid.</span></span> <span data-ttu-id="5b11d-109">由于每个时区应始终按键名称进行标识, 因此此成员的值应始终为**TZDEFINITION_FLAG_VALID_KEYNAME**。</span><span class="sxs-lookup"><span data-stu-id="5b11d-109">Because each time zone should always be identified by a key name, this member should always have the value **TZDEFINITION_FLAG_VALID_KEYNAME**.</span></span>
    
<span data-ttu-id="5b11d-110">_pwszKeyName_</span><span class="sxs-lookup"><span data-stu-id="5b11d-110">_pwszKeyName_</span></span>
  
> <span data-ttu-id="5b11d-111">Windows 注册表中此时区的键的名称。</span><span class="sxs-lookup"><span data-stu-id="5b11d-111">The name of the key for this time zone in the Windows registry.</span></span> <span data-ttu-id="5b11d-112">此名称不得本地化。</span><span class="sxs-lookup"><span data-stu-id="5b11d-112">This name must not be localized.</span></span> <span data-ttu-id="5b11d-113">它的最大大小为**MAX_PATH**, 在 windows 软件开发工具包 (SDK) 头文件 windows .h 中进行了定义。</span><span class="sxs-lookup"><span data-stu-id="5b11d-113">It has a maximum size of **MAX_PATH**, which is defined in the Windows Software Development Kit (SDK) header file windows.h.</span></span> 
    
<span data-ttu-id="5b11d-114">_cRules_</span><span class="sxs-lookup"><span data-stu-id="5b11d-114">_cRules_</span></span>
  
> <span data-ttu-id="5b11d-115">此定义的时区规则数。</span><span class="sxs-lookup"><span data-stu-id="5b11d-115">The number of time zone rules for this definition.</span></span> <span data-ttu-id="5b11d-116">最大规则数为**TZ_MAX_RULES**。</span><span class="sxs-lookup"><span data-stu-id="5b11d-116">The maximum number of rules is **TZ_MAX_RULES**.</span></span> 
    
<span data-ttu-id="5b11d-117">_rgRules_</span><span class="sxs-lookup"><span data-stu-id="5b11d-117">_rgRules_</span></span>
  
> <span data-ttu-id="5b11d-118">描述班次发生时间的规则数组。</span><span class="sxs-lookup"><span data-stu-id="5b11d-118">An array of rules that describe when shifts occur.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5b11d-119">注解</span><span class="sxs-lookup"><span data-stu-id="5b11d-119">Remarks</span></span>

<span data-ttu-id="5b11d-120">*rgRules*中必须至少有一个规则。</span><span class="sxs-lookup"><span data-stu-id="5b11d-120">There must be at least one rule in  *rgRules*  .</span></span> <span data-ttu-id="5b11d-121">在第二个规则启动前, *rgRules*中的第一个规则被视为要使用的规则, 而不考虑第一个规则上的*stStart* 。</span><span class="sxs-lookup"><span data-stu-id="5b11d-121">The first rule in  *rgRules*  is considered to be the rule to use until the second rule starts, regardless of the  *stStart*  on the first rule.</span></span> 
  
<span data-ttu-id="5b11d-122">应从最旧到最新对规则进行排序。</span><span class="sxs-lookup"><span data-stu-id="5b11d-122">The rules should be sorted from oldest to newest.</span></span> <span data-ttu-id="5b11d-123">规则之间不允许重叠, 因此在新规则开始时, 之前的规则将被认为是结束。</span><span class="sxs-lookup"><span data-stu-id="5b11d-123">There is no overlap allowed between rules, so a prior rule is deemed to end when a new rule starts.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b11d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b11d-124">See also</span></span>

- [<span data-ttu-id="5b11d-125">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="5b11d-125">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="5b11d-126">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="5b11d-126">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [<span data-ttu-id="5b11d-127">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="5b11d-127">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)

