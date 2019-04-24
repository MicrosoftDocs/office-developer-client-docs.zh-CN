---
title: ISocialSessionUnFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66c83041-ee83-41d5-b9dc-a4dc4c670f82
description: 删除由 userID 参数标识为社交网络上的友元的人员。
ms.openlocfilehash: c276a9e5af18f7e4a3afbaa66d366d55de460a58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336776"
---
# <a name="isocialsessionunfollowperson"></a><span data-ttu-id="6aa0d-103">ISocialSession::UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="6aa0d-103">ISocialSession::UnFollowPerson</span></span>

<span data-ttu-id="6aa0d-104">删除由_userID_参数标识为社交网络上的友元的人员。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-104">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span> 
  
```cpp
HRESULT _stdcall UnFollowPerson([in] BSTR userID);
```

## <a name="parameters"></a><span data-ttu-id="6aa0d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6aa0d-105">Parameters</span></span>

<span data-ttu-id="6aa0d-106">_userID_</span><span class="sxs-lookup"><span data-stu-id="6aa0d-106">_userID_</span></span>
  
> <span data-ttu-id="6aa0d-107">实时包含人员的社交网络用户 ID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-107">[in] A string that contains a social network user ID for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6aa0d-108">注解</span><span class="sxs-lookup"><span data-stu-id="6aa0d-108">Remarks</span></span>

<span data-ttu-id="6aa0d-109">_userID_参数必须是社交网络上的人员的有效用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-109">The  _userID_ parameter must be a valid user ID for the person on the social network.</span></span> 
  
<span data-ttu-id="6aa0d-110">如果 Outlook Social Connector (.osc) 提供程序将**doNotFollowPerson**中的**功能**设置为**true** , 则在传入的用户 ID 与网络上的用户不匹配的情况下, 提供程序必须返回 OSC_E_NOT_FOUND 错误。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-110">If the Outlook Social Connector (OSC) provider has set **doNotFollowPerson** as **true** in the XML for **capabilities**, the provider must return the OSC_E_NOT_FOUND error in the case that the user ID passed in does not match a user on the network.</span></span> <span data-ttu-id="6aa0d-111">如果提供程序在**功能**中将**doNotFollowPerson**设置为**false** , 则提供程序应返回 OSC_E_FAIL 错误。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-111">If the provider has set **doNotFollowPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span> <span data-ttu-id="6aa0d-112">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa0d-112">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6aa0d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa0d-113">See also</span></span>

- [<span data-ttu-id="6aa0d-114">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6aa0d-114">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

