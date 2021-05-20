---
title: ISocialSession2FollowPersonEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17b4af7f-7967-422b-996c-792705c93ad3
description: 将 emailAddresses 和 displayName 参数标识的人添加为社交网络上登录的用户的好友。
ms.openlocfilehash: b44b442ba928b48411e5b1fc8a0c8b76477022ae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429829"
---
# <a name="isocialsession2followpersonex"></a><span data-ttu-id="fdf97-103">ISocialSession2::FollowPersonEx</span><span class="sxs-lookup"><span data-stu-id="fdf97-103">ISocialSession2::FollowPersonEx</span></span>

<span data-ttu-id="fdf97-104">将  _emailAddresses_ 和  _displayName_ 参数标识的人添加为社交网络上登录的用户的好友。</span><span class="sxs-lookup"><span data-stu-id="fdf97-104">Adds the person identified by the  _emailAddresses_ and  _displayName_ parameters as a friend for the logged-on user on the social network.</span></span> 
  
```cpp
HRESULT _stdcall FollowPersonEx([in] SAFEARRAY(BSTR) emailAddresses, [in] BSTR displayName);
```

## <a name="parameters"></a><span data-ttu-id="fdf97-105">参数</span><span class="sxs-lookup"><span data-stu-id="fdf97-105">Parameters</span></span>

<span data-ttu-id="fdf97-106">_emailAddresses_</span><span class="sxs-lookup"><span data-stu-id="fdf97-106">_emailAddresses_</span></span>
  
> <span data-ttu-id="fdf97-107">[in]包含社交网络上某个人的一个或多个有效 SMTP 地址的数组。</span><span class="sxs-lookup"><span data-stu-id="fdf97-107">[in] An array that contains one or multiple valid SMTP addresses for a person on the social network.</span></span>
    
<span data-ttu-id="fdf97-108">_displayName_</span><span class="sxs-lookup"><span data-stu-id="fdf97-108">_displayName_</span></span>
  
> <span data-ttu-id="fdf97-109">[in]包含要添加显示名称好友的联系人的字符串。</span><span class="sxs-lookup"><span data-stu-id="fdf97-109">[in] A string that contains the display name of the person to be added as a friend.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fdf97-110">备注</span><span class="sxs-lookup"><span data-stu-id="fdf97-110">Remarks</span></span>

<span data-ttu-id="fdf97-111">如果 Outlook Social Connector (OSC) 在 **emailAddresses** 参数的数组中提供的 SMTP 地址多于 SMTP 地址，则 OSC 提供程序可以假定第一个元素是主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdf97-111">If the Outlook Social Connector (OSC) provides more than on SMTP address in the array in the **emailAddresses** parameter, the OSC provider can assume the first element is the primary SMTP address.</span></span> 
  
<span data-ttu-id="fdf97-112">如果提供程序在功能 **XML** 中将 **followPerson** 元素设置为 **true，**_并且 emailAddresses_ 的所有元素都不匹配网络用户，则提供程序必须返回 OSC_E_NOT_FOUND 错误。</span><span class="sxs-lookup"><span data-stu-id="fdf97-112">If the provider has set the **followPerson** element as **true** in the **capabilities** XML, and none of the elements for  _emailAddresses_ match a user on the network, the provider must return the OSC_E_NOT_FOUND error.</span></span> <span data-ttu-id="fdf97-113">如果提供程序在功能中将 **followPerson** 设置为 **false，** 则提供程序应返回OSC_E_FAIL错误。</span><span class="sxs-lookup"><span data-stu-id="fdf97-113">If the provider has set **followPerson** as **false** in **capabilities**, the provider should return the OSC_E_FAIL error.</span></span> 
  
<span data-ttu-id="fdf97-114">如果 **FollowPersonEx** 方法成功，则提供程序可以使用  _displayName_ 参数中的字符串寻址任何后续好友确认电子邮件中的人员，而不是通过 SMTP 地址寻址该人员。</span><span class="sxs-lookup"><span data-stu-id="fdf97-114">If the **FollowPersonEx** method succeeds, the provider can use the string in the  _displayName_ parameter to address the person in any subsequent friend-confirmation email, rather than addressing the person by the SMTP address.</span></span> <span data-ttu-id="fdf97-115">另一方面，提供程序必须能够处理为  _displayName_ 参数传递空字符串的 OSC。</span><span class="sxs-lookup"><span data-stu-id="fdf97-115">On the other hand, the provider must be able to handle the OSC passing an empty string for the  _displayName_ parameter.</span></span> 
  
<span data-ttu-id="fdf97-116">如果提供程序实现 [ISocialSession2](isocialsession2iunknown.md) 接口，并且在功能 XML 中将 **followPerson** 设置为 **true，** 则 OSC 将调用 **FollowPersonEx** 而不是 [ISocialSession：：FollowPerson](isocialsession-followperson.md)。</span><span class="sxs-lookup"><span data-stu-id="fdf97-116">If the provider implements the [ISocialSession2](isocialsession2iunknown.md) interface and has set **followPerson** as **true** in the capabilities XML, the OSC calls **FollowPersonEx** instead of [ISocialSession::FollowPerson](isocialsession-followperson.md).</span></span> <span data-ttu-id="fdf97-117">如果提供程序将 **followPerson** 设置为 **true，** 但不实现 **ISocialSession2** 接口，或者 **FollowPersonEx** 返回 OSC_E_NOTIMPL 错误，OSC 将调用 **ISocialSession：：FollowPerson**。</span><span class="sxs-lookup"><span data-stu-id="fdf97-117">If the provider has set **followPerson** as **true** but does not implement the **ISocialSession2** interface, or **FollowPersonEx** returns the OSC_E_NOTIMPL error, the OSC calls **ISocialSession::FollowPerson**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdf97-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdf97-118">See also</span></span>

- [<span data-ttu-id="fdf97-119">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fdf97-119">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)

