---
title: ISocialSessionUnFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66c83041-ee83-41d5-b9dc-a4dc4c670f82
description: 删除为社交网络上朋友 userID 参数标识的人员。
ms.openlocfilehash: 8b9a1e4f903e4bc805481b8679481103ea1ec82c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779242"
---
# <a name="isocialsessionunfollowperson"></a><span data-ttu-id="1411f-103">ISocialSession::UnFollowPerson</span><span class="sxs-lookup"><span data-stu-id="1411f-103">ISocialSession::UnFollowPerson</span></span>

<span data-ttu-id="1411f-104">删除为社交网络上朋友_userID_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="1411f-104">Removes the person identified by the  _userID_ parameter as a friend on the social network.</span></span> 
  
```cpp
HRESULT _stdcall UnFollowPerson([in] BSTR userID);
```

## <a name="parameters"></a><span data-ttu-id="1411f-105">参数</span><span class="sxs-lookup"><span data-stu-id="1411f-105">Parameters</span></span>

<span data-ttu-id="1411f-106">_用户 Id_</span><span class="sxs-lookup"><span data-stu-id="1411f-106">_userID_</span></span>
  
> <span data-ttu-id="1411f-107">[in]一个字符串，包含社交网络用户 ID 的人员。</span><span class="sxs-lookup"><span data-stu-id="1411f-107">[in] A string that contains a social network user ID for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1411f-108">说明</span><span class="sxs-lookup"><span data-stu-id="1411f-108">Remarks</span></span>

<span data-ttu-id="1411f-109">_UserID_参数必须为有效的用户 ID 的社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="1411f-109">The  _userID_ parameter must be a valid user ID for the person on the social network.</span></span> 
  
<span data-ttu-id="1411f-110">如果 Outlook Social Connector (OSC) 提供程序已设为**true** **功能**的 XML **doNotFollowPerson** ，提供程序必须在的用户中传递 ID 不匹配网络上的用户的情况下返回 OSC_E_NOT_FOUND 错误。</span><span class="sxs-lookup"><span data-stu-id="1411f-110">If the Outlook Social Connector (OSC) provider has set **doNotFollowPerson** as **true** in the XML for **capabilities**, the provider must return the OSC_E_NOT_FOUND error in the case that the user ID passed in does not match a user on the network.</span></span> <span data-ttu-id="1411f-111">如果提供程序已将**doNotFollowPerson**设置为**false** ，在**功能**中，提供程序应返回 OSC_E_FAIL 错误。</span><span class="sxs-lookup"><span data-stu-id="1411f-111">If the provider has set **doNotFollowPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span> <span data-ttu-id="1411f-112">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="1411f-112">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1411f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1411f-113">See also</span></span>

- [<span data-ttu-id="1411f-114">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1411f-114">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

