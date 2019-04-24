---
title: Gender
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f60c65e3-b55f-cb68-746e-d0a8cd862d4d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 042216df309e98f35ed0ad71742e46300ebb06da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342579"
---
# <a name="gender"></a><span data-ttu-id="7ae21-103">Gender</span><span class="sxs-lookup"><span data-stu-id="7ae21-103">Gender</span></span>

  
  
<span data-ttu-id="7ae21-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ae21-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ae21-105">指定邮件用户的性别的可能值。</span><span class="sxs-lookup"><span data-stu-id="7ae21-105">Specifies the possible values for the gender of a messaging user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7ae21-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7ae21-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="7ae21-107">成员</span><span class="sxs-lookup"><span data-stu-id="7ae21-107">Members</span></span>

 <span data-ttu-id="7ae21-108">_genderMin_</span><span class="sxs-lookup"><span data-stu-id="7ae21-108">_genderMin_</span></span>
  
> <span data-ttu-id="7ae21-109">为性别支持的最小不同值数。</span><span class="sxs-lookup"><span data-stu-id="7ae21-109">The minimum number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="7ae21-110">_genderUnspecified_</span><span class="sxs-lookup"><span data-stu-id="7ae21-110">_genderUnspecified_</span></span>
  
> <span data-ttu-id="7ae21-111">不指定邮件用户的性别。</span><span class="sxs-lookup"><span data-stu-id="7ae21-111">The gender is not specified for the messaging user.</span></span>
    
 <span data-ttu-id="7ae21-112">_genderFemale_</span><span class="sxs-lookup"><span data-stu-id="7ae21-112">_genderFemale_</span></span>
  
> <span data-ttu-id="7ae21-113">邮件用户是女。</span><span class="sxs-lookup"><span data-stu-id="7ae21-113">The messaging user is female.</span></span>
    
 <span data-ttu-id="7ae21-114">_genderMale_</span><span class="sxs-lookup"><span data-stu-id="7ae21-114">_genderMale_</span></span>
  
> <span data-ttu-id="7ae21-115">邮件用户是男。</span><span class="sxs-lookup"><span data-stu-id="7ae21-115">The messaging user is male.</span></span>
    
 <span data-ttu-id="7ae21-116">_genderCount_</span><span class="sxs-lookup"><span data-stu-id="7ae21-116">_genderCount_</span></span>
  
> <span data-ttu-id="7ae21-117">性别支持的不同值的数量。</span><span class="sxs-lookup"><span data-stu-id="7ae21-117">The number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="7ae21-118">_genderMax_</span><span class="sxs-lookup"><span data-stu-id="7ae21-118">_genderMax_</span></span>
  
> <span data-ttu-id="7ae21-119">性别支持的最大不同值数。</span><span class="sxs-lookup"><span data-stu-id="7ae21-119">The maximum number of different values supported for the gender.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7ae21-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ae21-120">See also</span></span>



[<span data-ttu-id="7ae21-121">PidTagGender 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ae21-121">PidTagGender Canonical Property</span></span>](pidtaggender-canonical-property.md)

