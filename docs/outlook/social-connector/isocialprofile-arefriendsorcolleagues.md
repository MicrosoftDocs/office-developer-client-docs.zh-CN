---
title: ISocialProfileAreFriendsOrColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0b586cd-65f6-4792-851c-4d36eaeec56d
description: 确定指定的用户是否为朋友。
ms.openlocfilehash: 183e47bea70ed378947afb6a1d0e5561fb9307f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412560"
---
# <a name="isocialprofilearefriendsorcolleagues"></a><span data-ttu-id="a0f4a-103">ISocialProfile::AreFriendsOrColleagues</span><span class="sxs-lookup"><span data-stu-id="a0f4a-103">ISocialProfile::AreFriendsOrColleagues</span></span>

<span data-ttu-id="a0f4a-104">确定指定的用户是否为朋友。</span><span class="sxs-lookup"><span data-stu-id="a0f4a-104">Determines whether the specified users are friends.</span></span>
  
```cpp
HRESULT _stdcall AreFriendsOrColleagues(SAFEARRAY(BSTR) userIds, [out, retval] SAFEARRAY(VARIANT_BOOL)* results);
```

## <a name="parameters"></a><span data-ttu-id="a0f4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0f4a-105">Parameters</span></span>

<span data-ttu-id="a0f4a-106">_userIds_</span><span class="sxs-lookup"><span data-stu-id="a0f4a-106">_userIds_</span></span>
  
> <span data-ttu-id="a0f4a-107">实时一个结构, 指定与社交网络上的一组人员相对应的用户 ID 值的数组。</span><span class="sxs-lookup"><span data-stu-id="a0f4a-107">[in] A structure that specifies an array of user ID values that correspond to a set of persons on the social network.</span></span>
    
<span data-ttu-id="a0f4a-108">_引起_</span><span class="sxs-lookup"><span data-stu-id="a0f4a-108">_results_</span></span>
  
> <span data-ttu-id="a0f4a-109">排除指向指定布尔值数组的结构的指针, 指示_userIds_数组中的相应人员是否为友元。</span><span class="sxs-lookup"><span data-stu-id="a0f4a-109">[out] A pointer to structure that specifies an array of Boolean values, indicating whether the corresponding person in the  _userIds_ array is a friend.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a0f4a-110">说明</span><span class="sxs-lookup"><span data-stu-id="a0f4a-110">Remarks</span></span>

<span data-ttu-id="a0f4a-111">对于_userIds_参数的输入数组中表示的每个人员, 此方法设置_结果_参数的输出数组中对应的元素。</span><span class="sxs-lookup"><span data-stu-id="a0f4a-111">For each person represented in the input array of the  _userIds_ parameter, this method sets the corresponding element in the output array of the  _results_ parameter.</span></span> <span data-ttu-id="a0f4a-112">**如果为 true** , 则表示此人为朋友, **false**表示该人员不是朋友。</span><span class="sxs-lookup"><span data-stu-id="a0f4a-112">**true** indicates that the person is a friend, and **false** indicates that the person is not a friend.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a0f4a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0f4a-113">See also</span></span>

- [<span data-ttu-id="a0f4a-114">ISocialProfile : ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="a0f4a-114">ISocialProfile : ISocialPerson</span></span>](isocialprofileisocialperson.md)

