---
title: ISocialProfileAreFriendsOrColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0b586cd-65f6-4792-851c-4d36eaeec56d
description: 确定指定的用户是否朋友。
ms.openlocfilehash: 17e7864dc60bf99df2028e5f6c57f0619d880a8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779214"
---
# <a name="isocialprofilearefriendsorcolleagues"></a><span data-ttu-id="6e928-103">ISocialProfile::AreFriendsOrColleagues</span><span class="sxs-lookup"><span data-stu-id="6e928-103">ISocialProfile::AreFriendsOrColleagues</span></span>

<span data-ttu-id="6e928-104">确定指定的用户是否朋友。</span><span class="sxs-lookup"><span data-stu-id="6e928-104">Determines whether the specified users are friends.</span></span>
  
```cpp
HRESULT _stdcall AreFriendsOrColleagues(SAFEARRAY(BSTR) userIds, [out, retval] SAFEARRAY(VARIANT_BOOL)* results);
```

## <a name="parameters"></a><span data-ttu-id="6e928-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e928-105">Parameters</span></span>

<span data-ttu-id="6e928-106">_userIds_</span><span class="sxs-lookup"><span data-stu-id="6e928-106">_userIds_</span></span>
  
> <span data-ttu-id="6e928-107">[in]一个指定的对应一封社交网络上的用户 ID 值的数组的结构。</span><span class="sxs-lookup"><span data-stu-id="6e928-107">[in] A structure that specifies an array of user ID values that correspond to a set of persons on the social network.</span></span>
    
<span data-ttu-id="6e928-108">_结果_</span><span class="sxs-lookup"><span data-stu-id="6e928-108">_results_</span></span>
  
> <span data-ttu-id="6e928-109">[输出]一个指向指定布尔值，指示_userIds_数组中的相应人员是否朋友数组的结构。</span><span class="sxs-lookup"><span data-stu-id="6e928-109">[out] A pointer to structure that specifies an array of Boolean values, indicating whether the corresponding person in the  _userIds_ array is a friend.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="6e928-110">说明</span><span class="sxs-lookup"><span data-stu-id="6e928-110">Remarks</span></span>

<span data-ttu-id="6e928-111">对于表示_userIds_参数的输入数组中每个用户，此方法设置输出_结果_参数数组中对应的元素。</span><span class="sxs-lookup"><span data-stu-id="6e928-111">For each person represented in the input array of the  _userIds_ parameter, this method sets the corresponding element in the output array of the  _results_ parameter.</span></span> <span data-ttu-id="6e928-112">**true**指示人员朋友，并且该人员不朋友**false**指示。</span><span class="sxs-lookup"><span data-stu-id="6e928-112">**true** indicates that the person is a friend, and **false** indicates that the person is not a friend.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e928-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e928-113">See also</span></span>

- [<span data-ttu-id="6e928-114">ISocialProfile : ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="6e928-114">ISocialProfile : ISocialPerson</span></span>](isocialprofileisocialperson.md)

