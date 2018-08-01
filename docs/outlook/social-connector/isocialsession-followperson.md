---
title: ISocialSessionFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de7f56e2-c131-4955-b945-0a72043e0f5a
description: 添加为朋友社交网络登录用户的电子邮件地址参数标识的人员。
ms.openlocfilehash: 6dc289801c99f2f3bf1647e9c98c072d2f53d066
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779233"
---
# <a name="isocialsessionfollowperson"></a><span data-ttu-id="a76da-103">ISocialSession::FollowPerson</span><span class="sxs-lookup"><span data-stu-id="a76da-103">ISocialSession::FollowPerson</span></span>

<span data-ttu-id="a76da-104">添加为朋友社交网络登录用户的_电子邮件地址_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="a76da-104">Adds the person identified by the  _emailAddress_ parameter as a friend for the logged-on user on the social network.</span></span> 
  
```cpp
HRESULT _stdcall FollowPerson([in] BSTR emailAddress);
```

## <a name="parameters"></a><span data-ttu-id="a76da-105">参数</span><span class="sxs-lookup"><span data-stu-id="a76da-105">Parameters</span></span>

<span data-ttu-id="a76da-106">_emailAddress_</span><span class="sxs-lookup"><span data-stu-id="a76da-106">_emailAddress_</span></span>
  
> <span data-ttu-id="a76da-107">[in]一个字符串，包含某个人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a76da-107">[in] A string that contains an email address of a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a76da-108">说明</span><span class="sxs-lookup"><span data-stu-id="a76da-108">Remarks</span></span>

<span data-ttu-id="a76da-109">_EmailAddress_参数必须为有效的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="a76da-109">The  _emailAddress_ parameter must be a valid SMTP address.</span></span> <span data-ttu-id="a76da-110">如果 Outlook Social Connector (OSC) 提供程序已经**followPerson**方法为**true**设置式**功能**，并且_电子邮件地址_的参数与网络上的用户不匹配，则提供程序必须返回 OSC_E_NOT_FOUND错误。</span><span class="sxs-lookup"><span data-stu-id="a76da-110">If the Outlook Social Connector (OSC) provider has set the **followPerson** method as **true** in **capabilities**, and the argument for  _emailAddress_ does not match a user on the network, the provider must return the OSC_E_NOT_FOUND error.</span></span> <span data-ttu-id="a76da-111">如果提供程序已将**followPerson**设置为**false** ，在**功能**中，提供程序应返回 OSC_E_FAIL 错误。</span><span class="sxs-lookup"><span data-stu-id="a76da-111">If the provider has set **followPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span>
  
<span data-ttu-id="a76da-112">OSC 提供程序实现[ISocialSession2](isocialsession2iunknown.md)接口和已在**功能**中**followPerson**设为**true** ，如果将而不是**ISocialSession::FollowPerson 调用[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)**.</span><span class="sxs-lookup"><span data-stu-id="a76da-112">If the provider implements the [ISocialSession2](isocialsession2iunknown.md) interface and has set **followPerson** as **true** in **capabilities**, the OSC will call [ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md) instead of **ISocialSession::FollowPerson**.</span></span> <span data-ttu-id="a76da-113">只要提供程序具有设置**OSC 提供程序未实现**ISocialSession2**接口，或者**ISocialSession2::FollowPersonEx**返回 OSC_E_NOTIMPL 错误，如果将调用**ISocialSession::FollowPerson**followPerson**作为**true** **功能**。</span><span class="sxs-lookup"><span data-stu-id="a76da-113">If the provider does not implement the **ISocialSession2** interface, or **ISocialSession2::FollowPersonEx** returns the OSC_E_NOTIMPL error, the OSC will call **ISocialSession::FollowPerson** as long as the provider has set **followPerson** as **true** in **capabilities**.</span></span> <span data-ttu-id="a76da-114">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="a76da-114">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
<span data-ttu-id="a76da-115">在决定是否要实现**ISocalSession::FollowPerson**或**ISocialSession2::FollowPersonEx**，您应考虑您的提供商所需的其他方法在**ISocialSession2**，以及是否可以使用_djsplayName_中**FollowPersonEx**参数。</span><span class="sxs-lookup"><span data-stu-id="a76da-115">In deciding whether to implement **ISocalSession::FollowPerson** or **ISocialSession2::FollowPersonEx**, you should consider whether your provider needs the other methods in **ISocialSession2**, and whether you can use the  _djsplayName_ parameter in **FollowPersonEx**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a76da-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a76da-116">See also</span></span>

- [<span data-ttu-id="a76da-117">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a76da-117">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

