---
title: ISocialSessionFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de7f56e2-c131-4955-b945-0a72043e0f5a
description: 将 emailAddress 参数标识的人员添加为社交网络上已登录用户的友元。
ms.openlocfilehash: 849085bd40788039a96ac159fd76a5e252395916
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423256"
---
# <a name="isocialsessionfollowperson"></a><span data-ttu-id="91a32-103">ISocialSession::FollowPerson</span><span class="sxs-lookup"><span data-stu-id="91a32-103">ISocialSession::FollowPerson</span></span>

<span data-ttu-id="91a32-104">将_emailAddress_参数标识的人员添加为社交网络上已登录用户的友元。</span><span class="sxs-lookup"><span data-stu-id="91a32-104">Adds the person identified by the  _emailAddress_ parameter as a friend for the logged-on user on the social network.</span></span> 
  
```cpp
HRESULT _stdcall FollowPerson([in] BSTR emailAddress);
```

## <a name="parameters"></a><span data-ttu-id="91a32-105">参数</span><span class="sxs-lookup"><span data-stu-id="91a32-105">Parameters</span></span>

<span data-ttu-id="91a32-106">_emailAddress_</span><span class="sxs-lookup"><span data-stu-id="91a32-106">_emailAddress_</span></span>
  
> <span data-ttu-id="91a32-107">实时包含某人的电子邮件地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="91a32-107">[in] A string that contains an email address of a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="91a32-108">说明</span><span class="sxs-lookup"><span data-stu-id="91a32-108">Remarks</span></span>

<span data-ttu-id="91a32-109">_emailAddress_参数必须是有效的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="91a32-109">The  _emailAddress_ parameter must be a valid SMTP address.</span></span> <span data-ttu-id="91a32-110">如果 Outlook Social Connector (.osc) 提供程序在**功能**中将**followPerson**方法设置为**true** , 并且_emailAddress_的参数与网络上的用户不匹配, 则该提供程序必须返回 OSC_E_NOT_FOUND误差.</span><span class="sxs-lookup"><span data-stu-id="91a32-110">If the Outlook Social Connector (OSC) provider has set the **followPerson** method as **true** in **capabilities**, and the argument for  _emailAddress_ does not match a user on the network, the provider must return the OSC_E_NOT_FOUND error.</span></span> <span data-ttu-id="91a32-111">如果提供程序在**功能**中将**followPerson**设置为**false** , 则提供程序应返回 OSC_E_FAIL 错误。</span><span class="sxs-lookup"><span data-stu-id="91a32-111">If the provider has set **followPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span>
  
<span data-ttu-id="91a32-112">如果提供程序实现了[ISocialSession2](isocialsession2iunknown.md)接口, 并在**功能**中将**followPerson**设置为**true** , 则该 .osc 将调用[ISocialSession2:: FollowPersonEx](isocialsession2-followpersonex.md)而不是**ISocialSession:: followPerson**.</span><span class="sxs-lookup"><span data-stu-id="91a32-112">If the provider implements the [ISocialSession2](isocialsession2iunknown.md) interface and has set **followPerson** as **true** in **capabilities**, the OSC will call [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md) instead of **ISocialSession::FollowPerson**.</span></span> <span data-ttu-id="91a32-113">如果提供程序未实现**ISocialSession2**接口, 或者**ISocialSession2:: FollowPersonEx**返回 OSC_E_NOTIMPL 错误, 则在提供程序已设置\*\*\*\* **的情况下, .osc 将调用 ISocialSession:: FollowPerson\*\*\*\*功能**中的 followPerson 为**true** 。</span><span class="sxs-lookup"><span data-stu-id="91a32-113">If the provider does not implement the **ISocialSession2** interface, or **ISocialSession2::FollowPersonEx** returns the OSC_E_NOTIMPL error, the OSC will call **ISocialSession::FollowPerson** as long as the provider has set **followPerson** as **true** in **capabilities**.</span></span> <span data-ttu-id="91a32-114">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="91a32-114">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
<span data-ttu-id="91a32-115">在决定是否实现**ISocalSession:: FollowPerson**或**ISocialSession2:: FollowPersonEx**时, 应考虑提供程序中的其他方法是否需要**ISocialSession2**中的其他方法, 以及是否可以使用__ **FollowPersonEx**中的 djsplayName 参数。</span><span class="sxs-lookup"><span data-stu-id="91a32-115">In deciding whether to implement **ISocalSession::FollowPerson** or **ISocialSession2::FollowPersonEx**, you should consider whether your provider needs the other methods in **ISocialSession2**, and whether you can use the  _djsplayName_ parameter in **FollowPersonEx**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91a32-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91a32-116">See also</span></span>

- [<span data-ttu-id="91a32-117">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="91a32-117">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

