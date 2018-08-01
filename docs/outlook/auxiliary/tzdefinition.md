---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 代表包括夏时制的所有历史、 当前和将来的时区 shift 规则整个所在的时区。
ms.openlocfilehash: f436216f5da882ea8ac144e6bd384e51e31abb8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774473"
---
# <a name="tzdefinition"></a><span data-ttu-id="b4a07-103">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="b4a07-103">TZDEFINITION</span></span>

<span data-ttu-id="b4a07-104">代表包括夏时制的所有历史、 当前和将来的时区 shift 规则整个所在的时区。</span><span class="sxs-lookup"><span data-stu-id="b4a07-104">Represents an entire time zone including all historical, current, and future time zone shift rules for daylight saving time.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b4a07-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b4a07-105">Quick info</span></span>

```cpp
typedef struct { 
    WORD     wFlags;  
    LPWSTR   pwszKeyName; 
    WORD     cRules; 
    TZRULE*  rgRules; 
} TZDEFINITION;
```

## <a name="members"></a><span data-ttu-id="b4a07-106">Members</span><span class="sxs-lookup"><span data-stu-id="b4a07-106">Members</span></span>

<span data-ttu-id="b4a07-107">_wFlags_</span><span class="sxs-lookup"><span data-stu-id="b4a07-107">_wFlags_</span></span>
  
> <span data-ttu-id="b4a07-108">指示键名值，该值代表在 Windows 注册表中的时区有效。</span><span class="sxs-lookup"><span data-stu-id="b4a07-108">Indicates that the key name that represents the time zone in the Windows registry is valid.</span></span> <span data-ttu-id="b4a07-109">因为每个时区始终应由项的名称，此成员应始终具有值**TZDEFINITION_FLAG_VALID_KEYNAME**。</span><span class="sxs-lookup"><span data-stu-id="b4a07-109">Because each time zone should always be identified by a key name, this member should always have the value **TZDEFINITION_FLAG_VALID_KEYNAME**.</span></span>
    
<span data-ttu-id="b4a07-110">_pwszKeyName_</span><span class="sxs-lookup"><span data-stu-id="b4a07-110">_pwszKeyName_</span></span>
  
> <span data-ttu-id="b4a07-111">此时区在 Windows 注册表中项的名称。</span><span class="sxs-lookup"><span data-stu-id="b4a07-111">The name of the key for this time zone in the Windows registry.</span></span> <span data-ttu-id="b4a07-112">此名称必须不进行本地化。</span><span class="sxs-lookup"><span data-stu-id="b4a07-112">This name must not be localized.</span></span> <span data-ttu-id="b4a07-113">它具有**MAX_PATH**，在 Windows 软件开发工具包 (SDK) 标头文件 windows.h 中定义的最大大小。</span><span class="sxs-lookup"><span data-stu-id="b4a07-113">It has a maximum size of **MAX_PATH**, which is defined in the Windows Software Development Kit (SDK) header file windows.h.</span></span> 
    
<span data-ttu-id="b4a07-114">_cRules_</span><span class="sxs-lookup"><span data-stu-id="b4a07-114">_cRules_</span></span>
  
> <span data-ttu-id="b4a07-115">为此定义的时区规则的数目。</span><span class="sxs-lookup"><span data-stu-id="b4a07-115">The number of time zone rules for this definition.</span></span> <span data-ttu-id="b4a07-116">规则的最大数目是**TZ_MAX_RULES**。</span><span class="sxs-lookup"><span data-stu-id="b4a07-116">The maximum number of rules is **TZ_MAX_RULES**.</span></span> 
    
<span data-ttu-id="b4a07-117">_rgRules_</span><span class="sxs-lookup"><span data-stu-id="b4a07-117">_rgRules_</span></span>
  
> <span data-ttu-id="b4a07-118">规则描述引进发生的数组。</span><span class="sxs-lookup"><span data-stu-id="b4a07-118">An array of rules that describe when shifts occur.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b4a07-119">说明</span><span class="sxs-lookup"><span data-stu-id="b4a07-119">Remarks</span></span>

<span data-ttu-id="b4a07-120">*RgRules*中必须有至少一个规则。</span><span class="sxs-lookup"><span data-stu-id="b4a07-120">There must be at least one rule in  *rgRules*  .</span></span> <span data-ttu-id="b4a07-121">考虑为要使用直到开始的第二个规则的规则，无论*stStart*上的第一个规则， *rgRules*中的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="b4a07-121">The first rule in  *rgRules*  is considered to be the rule to use until the second rule starts, regardless of the  *stStart*  on the first rule.</span></span> 
  
<span data-ttu-id="b4a07-122">到最新，应从最早排序规则。</span><span class="sxs-lookup"><span data-stu-id="b4a07-122">The rules should be sorted from oldest to newest.</span></span> <span data-ttu-id="b4a07-123">允许规则，以便将前一个规则视为结束时开始一个新规则之间没有重叠。</span><span class="sxs-lookup"><span data-stu-id="b4a07-123">There is no overlap allowed between rules, so a prior rule is deemed to end when a new rule starts.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b4a07-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4a07-124">See also</span></span>

- [<span data-ttu-id="b4a07-125">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="b4a07-125">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="b4a07-126">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="b4a07-126">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [<span data-ttu-id="b4a07-127">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="b4a07-127">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)

