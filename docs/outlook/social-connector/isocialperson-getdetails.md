---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串，代表人员的详细信息，例如名字、姓氏和个人资料图片的 URL。
ms.openlocfilehash: 05cc2565ccd0688c7b8f4eccd6d8f42353d8743e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427330"
---
# <a name="isocialpersongetdetails"></a><span data-ttu-id="f20f1-103">ISocialPerson::GetDetails</span><span class="sxs-lookup"><span data-stu-id="f20f1-103">ISocialPerson::GetDetails</span></span>

<span data-ttu-id="f20f1-104">获取一个字符串，代表人员的详细信息，例如名字、姓氏和个人资料图片的 URL。</span><span class="sxs-lookup"><span data-stu-id="f20f1-104">Gets a string that represents details for the person, such as the first name, last name, and a URL to a profile picture.</span></span> 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a><span data-ttu-id="f20f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="f20f1-105">Parameters</span></span>

<span data-ttu-id="f20f1-106">_details_</span><span class="sxs-lookup"><span data-stu-id="f20f1-106">_details_</span></span>
  
> <span data-ttu-id="f20f1-107">[out]一个 XML 字符串值，表示人员的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f20f1-107">[out] An XML string value that represents the details for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f20f1-108">备注</span><span class="sxs-lookup"><span data-stu-id="f20f1-108">Remarks</span></span>

<span data-ttu-id="f20f1-109">返回 _的详细信息_ XML 字符串必须符合 **person** 的架构定义，如 Outlook Social Connector (OSC) 扩展的架构中定义。</span><span class="sxs-lookup"><span data-stu-id="f20f1-109">The returned  _details_ XML string must comply with the schema definition for **person**, as defined in the schema for Outlook Social Connector (OSC) provider extensibility.</span></span>
  
<span data-ttu-id="f20f1-110">如果 OSC 提供程序支持社交网络上好友的缓存或混合同步，OSC 将调用 **GetDetails。**</span><span class="sxs-lookup"><span data-stu-id="f20f1-110">The OSC calls **GetDetails** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="f20f1-111">当 OSC 最初获取已登录用户的好友活动时，它会调用[ISocialPerson：：GetFriendsAndColleagues，](isocialperson-getfriendsandcolleagues.md)将好友的信息存储在特定于社交网络的联系人文件夹中，位于登录用户的默认 Outlook 商店中。</span><span class="sxs-lookup"><span data-stu-id="f20f1-111">When the OSC initially gets friends' activities for the logged on user, it calls [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), and stores friends' information in a contacts folder specific to the social network, in the logged on user's default Outlook store.</span></span> <span data-ttu-id="f20f1-112">随后，OSC 不会调用 **GetFriendsAndColleagues** 或 **GetDetails，** 除非缓存的刷新间隔已过期。</span><span class="sxs-lookup"><span data-stu-id="f20f1-112">Subsequently the OSC does not call **GetFriendsAndColleagues** or **GetDetails** unless the refresh interval for the cache has expired.</span></span> <span data-ttu-id="f20f1-113">有关 OSC 如何在联系人文件夹中缓存好友信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="f20f1-113">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f20f1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f20f1-114">See also</span></span>

- [<span data-ttu-id="f20f1-115">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f20f1-115">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

