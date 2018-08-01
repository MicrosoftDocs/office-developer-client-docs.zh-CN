---
title: Gender
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f60c65e3-b55f-cb68-746e-d0a8cd862d4d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7abc62938b3c33e42adedfe8ccd66e072314e333
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775023"
---
# <a name="gender"></a><span data-ttu-id="651aa-103">Gender</span><span class="sxs-lookup"><span data-stu-id="651aa-103">Gender</span></span>

  
  
<span data-ttu-id="651aa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="651aa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="651aa-105">指定邮件用户的性别的可能值。</span><span class="sxs-lookup"><span data-stu-id="651aa-105">Specifies the possible values for the gender of a messaging user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="651aa-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="651aa-106">Quick info</span></span>

```cpp
enum Gender { 
    genderMin = 0, 
    genderUnspecified = genderMin, 
    genderFemale, 
    genderMale, 
    genderCount, 
    genderMax = genderCount - 1 
}; 

```

## <a name="members"></a><span data-ttu-id="651aa-107">Members</span><span class="sxs-lookup"><span data-stu-id="651aa-107">Members</span></span>

 <span data-ttu-id="651aa-108">_genderMin_</span><span class="sxs-lookup"><span data-stu-id="651aa-108">_genderMin_</span></span>
  
> <span data-ttu-id="651aa-109">支持的性别的不同值的最小数目。</span><span class="sxs-lookup"><span data-stu-id="651aa-109">The minimum number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="651aa-110">_genderUnspecified_</span><span class="sxs-lookup"><span data-stu-id="651aa-110">_genderUnspecified_</span></span>
  
> <span data-ttu-id="651aa-111">未指定邮件用户的性别。</span><span class="sxs-lookup"><span data-stu-id="651aa-111">The gender is not specified for the messaging user.</span></span>
    
 <span data-ttu-id="651aa-112">_genderFemale_</span><span class="sxs-lookup"><span data-stu-id="651aa-112">_genderFemale_</span></span>
  
> <span data-ttu-id="651aa-113">女消息用户。</span><span class="sxs-lookup"><span data-stu-id="651aa-113">The messaging user is female.</span></span>
    
 <span data-ttu-id="651aa-114">_genderMale_</span><span class="sxs-lookup"><span data-stu-id="651aa-114">_genderMale_</span></span>
  
> <span data-ttu-id="651aa-115">男性消息用户。</span><span class="sxs-lookup"><span data-stu-id="651aa-115">The messaging user is male.</span></span>
    
 <span data-ttu-id="651aa-116">_genderCount_</span><span class="sxs-lookup"><span data-stu-id="651aa-116">_genderCount_</span></span>
  
> <span data-ttu-id="651aa-117">支持的性别的不同值的数目。</span><span class="sxs-lookup"><span data-stu-id="651aa-117">The number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="651aa-118">_genderMax_</span><span class="sxs-lookup"><span data-stu-id="651aa-118">_genderMax_</span></span>
  
> <span data-ttu-id="651aa-119">支持的性别的不同值的最大数目。</span><span class="sxs-lookup"><span data-stu-id="651aa-119">The maximum number of different values supported for the gender.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="651aa-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="651aa-120">See also</span></span>



[<span data-ttu-id="651aa-121">PidTagGender 规范属性</span><span class="sxs-lookup"><span data-stu-id="651aa-121">PidTagGender Canonical Property</span></span>](pidtaggender-canonical-property.md)

