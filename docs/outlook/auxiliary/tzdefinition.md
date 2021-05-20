---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 表示包括夏令时的所有历史、当前和将来的时区班次规则在内的整个时区。
ms.openlocfilehash: 5f7000ecc1fa602b330670c2ee1c39f673a11a65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429339"
---
# <a name="tzdefinition"></a><span data-ttu-id="78dd3-103">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="78dd3-103">TZDEFINITION</span></span>

<span data-ttu-id="78dd3-104">表示包括夏令时的所有历史、当前和将来的时区班次规则在内的整个时区。</span><span class="sxs-lookup"><span data-stu-id="78dd3-104">Represents an entire time zone including all historical, current, and future time zone shift rules for daylight saving time.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="78dd3-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="78dd3-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD     wFlags;  
    LPWSTR   pwszKeyName; 
    WORD     cRules; 
    TZRULE*  rgRules; 
} TZDEFINITION;
```

## <a name="members"></a><span data-ttu-id="78dd3-106">成员</span><span class="sxs-lookup"><span data-stu-id="78dd3-106">Members</span></span>

<span data-ttu-id="78dd3-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="78dd3-107">_wFlags_</span></span>
  
> <span data-ttu-id="78dd3-108">指示表示注册表中时区Windows名称有效。</span><span class="sxs-lookup"><span data-stu-id="78dd3-108">Indicates that the key name that represents the time zone in the Windows registry is valid.</span></span> <span data-ttu-id="78dd3-109">由于每个时区应始终由键名称标识，因此此成员的值应始终为 **TZDEFINITION_FLAG_VALID_KEYNAME。**</span><span class="sxs-lookup"><span data-stu-id="78dd3-109">Because each time zone should always be identified by a key name, this member should always have the value **TZDEFINITION_FLAG_VALID_KEYNAME**.</span></span>
    
<span data-ttu-id="78dd3-110">_pwszKeyName_</span><span class="sxs-lookup"><span data-stu-id="78dd3-110">_pwszKeyName_</span></span>
  
> <span data-ttu-id="78dd3-111">注册表中此时区的项Windows名称。</span><span class="sxs-lookup"><span data-stu-id="78dd3-111">The name of the key for this time zone in the Windows registry.</span></span> <span data-ttu-id="78dd3-112">此名称不得本地化。</span><span class="sxs-lookup"><span data-stu-id="78dd3-112">This name must not be localized.</span></span> <span data-ttu-id="78dd3-113">它的最大大小为 **MAX_PATH**，这是在 Windows Sdk (SDK) 头文件 windows.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="78dd3-113">It has a maximum size of **MAX_PATH**, which is defined in the Windows Software Development Kit (SDK) header file windows.h.</span></span> 
    
<span data-ttu-id="78dd3-114">_cRules_</span><span class="sxs-lookup"><span data-stu-id="78dd3-114">_cRules_</span></span>
  
> <span data-ttu-id="78dd3-115">此定义的时区规则数。</span><span class="sxs-lookup"><span data-stu-id="78dd3-115">The number of time zone rules for this definition.</span></span> <span data-ttu-id="78dd3-116">最大规则数为 **TZ_MAX_RULES**。</span><span class="sxs-lookup"><span data-stu-id="78dd3-116">The maximum number of rules is **TZ_MAX_RULES**.</span></span> 
    
<span data-ttu-id="78dd3-117">_rgRules_</span><span class="sxs-lookup"><span data-stu-id="78dd3-117">_rgRules_</span></span>
  
> <span data-ttu-id="78dd3-118">描述何时发生班次的规则数组。</span><span class="sxs-lookup"><span data-stu-id="78dd3-118">An array of rules that describe when shifts occur.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="78dd3-119">备注</span><span class="sxs-lookup"><span data-stu-id="78dd3-119">Remarks</span></span>

<span data-ttu-id="78dd3-120">rgRules 中必须至少有  *一个规则*  。</span><span class="sxs-lookup"><span data-stu-id="78dd3-120">There must be at least one rule in  *rgRules*  .</span></span> <span data-ttu-id="78dd3-121">*rgRules* 中的第一个规则被视为第二个规则启动之前使用的规则，而不管第一个规则上的 *stStart* 是什么。</span><span class="sxs-lookup"><span data-stu-id="78dd3-121">The first rule in  *rgRules*  is considered to be the rule to use until the second rule starts, regardless of the  *stStart*  on the first rule.</span></span> 
  
<span data-ttu-id="78dd3-122">规则应按从旧到新排序。</span><span class="sxs-lookup"><span data-stu-id="78dd3-122">The rules should be sorted from oldest to newest.</span></span> <span data-ttu-id="78dd3-123">规则之间不允许重叠，因此当新规则启动时，以前的规则被视为结束。</span><span class="sxs-lookup"><span data-stu-id="78dd3-123">There is no overlap allowed between rules, so a prior rule is deemed to end when a new rule starts.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78dd3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78dd3-124">See also</span></span>

- [<span data-ttu-id="78dd3-125">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="78dd3-125">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="78dd3-126">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="78dd3-126">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [<span data-ttu-id="78dd3-127">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="78dd3-127">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)

