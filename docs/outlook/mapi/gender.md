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
ms.openlocfilehash: a74a6639023ae6ffddeabd03970b609e7b7babe1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588452"
---
# <a name="gender"></a><span data-ttu-id="d086a-103">Gender</span><span class="sxs-lookup"><span data-stu-id="d086a-103">Gender</span></span>

  
  
<span data-ttu-id="d086a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d086a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d086a-105">指定邮件用户的性别的可能值。</span><span class="sxs-lookup"><span data-stu-id="d086a-105">Specifies the possible values for the gender of a messaging user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d086a-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d086a-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="d086a-107">Members</span><span class="sxs-lookup"><span data-stu-id="d086a-107">Members</span></span>

 <span data-ttu-id="d086a-108">_genderMin_</span><span class="sxs-lookup"><span data-stu-id="d086a-108">_genderMin_</span></span>
  
> <span data-ttu-id="d086a-109">支持的性别的不同值的最小数目。</span><span class="sxs-lookup"><span data-stu-id="d086a-109">The minimum number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="d086a-110">_genderUnspecified_</span><span class="sxs-lookup"><span data-stu-id="d086a-110">_genderUnspecified_</span></span>
  
> <span data-ttu-id="d086a-111">未指定邮件用户的性别。</span><span class="sxs-lookup"><span data-stu-id="d086a-111">The gender is not specified for the messaging user.</span></span>
    
 <span data-ttu-id="d086a-112">_genderFemale_</span><span class="sxs-lookup"><span data-stu-id="d086a-112">_genderFemale_</span></span>
  
> <span data-ttu-id="d086a-113">女消息用户。</span><span class="sxs-lookup"><span data-stu-id="d086a-113">The messaging user is female.</span></span>
    
 <span data-ttu-id="d086a-114">_genderMale_</span><span class="sxs-lookup"><span data-stu-id="d086a-114">_genderMale_</span></span>
  
> <span data-ttu-id="d086a-115">男性消息用户。</span><span class="sxs-lookup"><span data-stu-id="d086a-115">The messaging user is male.</span></span>
    
 <span data-ttu-id="d086a-116">_genderCount_</span><span class="sxs-lookup"><span data-stu-id="d086a-116">_genderCount_</span></span>
  
> <span data-ttu-id="d086a-117">支持的性别的不同值的数目。</span><span class="sxs-lookup"><span data-stu-id="d086a-117">The number of different values supported for the gender.</span></span>
    
 <span data-ttu-id="d086a-118">_genderMax_</span><span class="sxs-lookup"><span data-stu-id="d086a-118">_genderMax_</span></span>
  
> <span data-ttu-id="d086a-119">支持的性别的不同值的最大数目。</span><span class="sxs-lookup"><span data-stu-id="d086a-119">The maximum number of different values supported for the gender.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d086a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d086a-120">See also</span></span>



[<span data-ttu-id="d086a-121">PidTagGender 规范属性</span><span class="sxs-lookup"><span data-stu-id="d086a-121">PidTagGender Canonical Property</span></span>](pidtaggender-canonical-property.md)

