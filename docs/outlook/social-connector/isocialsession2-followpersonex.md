---
title: ISocialSession2FollowPersonEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17b4af7f-7967-422b-996c-792705c93ad3
description: 添加为社交网络登录用户的朋友由 emailAddresses 和 displayName 参数标识的人员。
ms.openlocfilehash: 2f4df9afc4c769cce0502792373702c1281fcad7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779251"
---
# <a name="isocialsession2followpersonex"></a><span data-ttu-id="63f9f-103">ISocialSession2::FollowPersonEx</span><span class="sxs-lookup"><span data-stu-id="63f9f-103">ISocialSession2::FollowPersonEx</span></span>

<span data-ttu-id="63f9f-104">添加为社交网络登录用户的朋友由_emailAddresses_和_displayName_参数标识的人员。</span><span class="sxs-lookup"><span data-stu-id="63f9f-104">Adds the person identified by the  _emailAddresses_ and  _displayName_ parameters as a friend for the logged-on user on the social network.</span></span> 
  
```cpp
HRESULT _stdcall FollowPersonEx([in] SAFEARRAY(BSTR) emailAddresses, [in] BSTR displayName);
```

## <a name="parameters"></a><span data-ttu-id="63f9f-105">参数</span><span class="sxs-lookup"><span data-stu-id="63f9f-105">Parameters</span></span>

<span data-ttu-id="63f9f-106">_emailAddresses_</span><span class="sxs-lookup"><span data-stu-id="63f9f-106">_emailAddresses_</span></span>
  
> <span data-ttu-id="63f9f-107">[in]社交网络上的人员包含一个或多个有效的 SMTP 地址的数组。</span><span class="sxs-lookup"><span data-stu-id="63f9f-107">[in] An array that contains one or multiple valid SMTP addresses for a person on the social network.</span></span>
    
<span data-ttu-id="63f9f-108">_displayName_</span><span class="sxs-lookup"><span data-stu-id="63f9f-108">_displayName_</span></span>
  
> <span data-ttu-id="63f9f-109">[in]一个字符串，包含要添加为朋友的人员的显示名称。</span><span class="sxs-lookup"><span data-stu-id="63f9f-109">[in] A string that contains the display name of the person to be added as a friend.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="63f9f-110">说明</span><span class="sxs-lookup"><span data-stu-id="63f9f-110">Remarks</span></span>

<span data-ttu-id="63f9f-111">如果 Outlook Social Connector (OSC) 提供有关超过**emailAddresses**参数，OSC 提供程序中的数组中的 SMTP 地址可以假定的第一个元素的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="63f9f-111">If the Outlook Social Connector (OSC) provides more than on SMTP address in the array in the **emailAddresses** parameter, the OSC provider can assume the first element is the primary SMTP address.</span></span> 
  
<span data-ttu-id="63f9f-112">如果提供程序已经**followPerson**元素作为**true**设置中**功能**XML，并且无的元素的_emailAddresses_匹配网络上的用户，提供程序必须返回 OSC_E_NOT_FOUND 错误。</span><span class="sxs-lookup"><span data-stu-id="63f9f-112">If the provider has set the **followPerson** element as **true** in the **capabilities** XML, and none of the elements for  _emailAddresses_ match a user on the network, the provider must return the OSC_E_NOT_FOUND error.</span></span> <span data-ttu-id="63f9f-113">如果提供程序已将**followPerson**设置为**false** ，在**功能**中，提供程序应返回 OSC_E_FAIL 错误。</span><span class="sxs-lookup"><span data-stu-id="63f9f-113">If the provider has set **followPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span> 
  
<span data-ttu-id="63f9f-114">如果**FollowPersonEx**方法成功，提供程序可以使用字符串_displayName_参数中解决任何后续的好朋友确认电子邮件，而不是解决此人的 SMTP 地址中的人员。</span><span class="sxs-lookup"><span data-stu-id="63f9f-114">If the **FollowPersonEx** method succeeds, the provider can use the string in the  _displayName_ parameter to address the person in any subsequent friend-confirmation email, rather than addressing the person by the SMTP address.</span></span> <span data-ttu-id="63f9f-115">另一方面，提供程序必须能够处理 OSC 传递的_displayName_参数为空字符串。</span><span class="sxs-lookup"><span data-stu-id="63f9f-115">On the other hand, the provider must be able to handle the OSC passing an empty string for the  _displayName_ parameter.</span></span> 
  
<span data-ttu-id="63f9f-116">如果提供程序实现[ISocialSession2](isocialsession2iunknown.md)接口，并且已将**followPerson**设置为**true**的功能 XML 中，OSC 调用**FollowPersonEx**而不是[ISocialSession::FollowPerson](isocialsession-followperson.md)。</span><span class="sxs-lookup"><span data-stu-id="63f9f-116">If the provider implements the [ISocialSession2](isocialsession2iunknown.md) interface and has set **followPerson** as **true** in the capabilities XML, the OSC calls **FollowPersonEx** instead of [ISocialSession::FollowPerson](isocialsession-followperson.md).</span></span> <span data-ttu-id="63f9f-117">如果提供程序已将**followPerson**设置为**true** ，但未实现**ISocialSession2**接口，或**FollowPersonEx**返回 OSC_E_NOTIMPL 错误，OSC 调用**ISocialSession::FollowPerson**。</span><span class="sxs-lookup"><span data-stu-id="63f9f-117">If the provider has set **followPerson** as **true** but does not implement the **ISocialSession2** interface, or **FollowPersonEx** returns the OSC_E_NOTIMPL error, the OSC calls **ISocialSession::FollowPerson**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63f9f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63f9f-118">See also</span></span>

- [<span data-ttu-id="63f9f-119">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="63f9f-119">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)

