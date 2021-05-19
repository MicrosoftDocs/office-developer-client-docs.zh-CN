---
title: ISocialSessionUnFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66c83041-ee83-41d5-b9dc-a4dc4c670f82
description: 删除 userID 参数标识为社交网络上好友的人。
ms.openlocfilehash: c276a9e5af18f7e4a3afbaa66d366d55de460a58
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418433"
---
# <a name="isocialsessionunfollowperson"></a><span data-ttu-id="511ca-103">ISocialSession::UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="511ca-103">ISocialSession::UnFollowPerson</span></span>

<span data-ttu-id="511ca-104">删除  _userID_ 参数标识为社交网络上好友的人。</span><span class="sxs-lookup"><span data-stu-id="511ca-104">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span> 
  
```cpp
HRESULT _stdcall UnFollowPerson([in] BSTR userID);
```

## <a name="parameters"></a><span data-ttu-id="511ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="511ca-105">Parameters</span></span>

<span data-ttu-id="511ca-106">_userID_</span><span class="sxs-lookup"><span data-stu-id="511ca-106">_userID_</span></span>
  
> <span data-ttu-id="511ca-107">[in]包含用户的社交网络用户 ID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="511ca-107">[in] A string that contains a social network user ID for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="511ca-108">备注</span><span class="sxs-lookup"><span data-stu-id="511ca-108">Remarks</span></span>

<span data-ttu-id="511ca-109">_userID_ 参数必须是社交网络上人员的有效用户 ID。</span><span class="sxs-lookup"><span data-stu-id="511ca-109">The  _userID_ parameter must be a valid user ID for the person on the social network.</span></span> 
  
<span data-ttu-id="511ca-110">如果 Outlook Social Connector (OSC) 提供程序在功能的 XML 中将 **doNotFollowPerson** 设置为 **true，** 则当传入的用户 ID 与网络上用户不匹配时，提供程序必须返回 OSC_E_NOT_FOUND 错误。</span><span class="sxs-lookup"><span data-stu-id="511ca-110">If the Outlook Social Connector (OSC) provider has set **doNotFollowPerson** as **true** in the XML for **capabilities**, the provider must return the OSC_E_NOT_FOUND error in the case that the user ID passed in does not match a user on the network.</span></span> <span data-ttu-id="511ca-111">如果提供程序在功能中将 **doNotFollowPerson** 设置为 **false，** 则提供程序应返回OSC_E_FAIL错误。</span><span class="sxs-lookup"><span data-stu-id="511ca-111">If the provider has set **doNotFollowPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span> <span data-ttu-id="511ca-112">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="511ca-112">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="511ca-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="511ca-113">See also</span></span>

- [<span data-ttu-id="511ca-114">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="511ca-114">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

