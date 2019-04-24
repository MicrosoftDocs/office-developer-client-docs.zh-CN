---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串, 表示人员的详细信息, 如名字、姓氏和指向个人资料图片的 URL。
ms.openlocfilehash: 05cc2565ccd0688c7b8f4eccd6d8f42353d8743e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286141"
---
# <a name="isocialpersongetdetails"></a><span data-ttu-id="bb586-103">ISocialPerson::GetDetails</span><span class="sxs-lookup"><span data-stu-id="bb586-103">ISocialPerson::GetDetails</span></span>

<span data-ttu-id="bb586-104">获取一个字符串, 表示人员的详细信息, 如名字、姓氏和指向个人资料图片的 URL。</span><span class="sxs-lookup"><span data-stu-id="bb586-104">Gets a string that represents details for the person, such as the first name, last name, and a URL to a profile picture.</span></span> 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a><span data-ttu-id="bb586-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb586-105">Parameters</span></span>

<span data-ttu-id="bb586-106">_details_</span><span class="sxs-lookup"><span data-stu-id="bb586-106">_details_</span></span>
  
> <span data-ttu-id="bb586-107">排除一个 XML 字符串值, 表示人员的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb586-107">[out] An XML string value that represents the details for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bb586-108">注解</span><span class="sxs-lookup"><span data-stu-id="bb586-108">Remarks</span></span>

<span data-ttu-id="bb586-109">返回的_详细信息_XML 字符串必须符合**人员**的架构定义, 如 Outlook Social Connector (.osc) 提供程序扩展性的架构中所定义。</span><span class="sxs-lookup"><span data-stu-id="bb586-109">The returned  _details_ XML string must comply with the schema definition for **person**, as defined in the schema for Outlook Social Connector (OSC) provider extensibility.</span></span>
  
<span data-ttu-id="bb586-110">如果 .osc 提供商支持社交网络上的友元缓存或混合同步, 则 .osc 调用**GetDetails** 。</span><span class="sxs-lookup"><span data-stu-id="bb586-110">The OSC calls **GetDetails** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="bb586-111">当 .osc 最初获得登录用户的朋友活动时, 它会调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), 并将朋友的信息存储在登录用户的默认 Outlook 存储区中的 "联系人" 文件夹中, 并将其存储在特定于社交网络的 "联系人" 文件夹中。.</span><span class="sxs-lookup"><span data-stu-id="bb586-111">When the OSC initially gets friends' activities for the logged on user, it calls [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), and stores friends' information in a contacts folder specific to the social network, in the logged on user's default Outlook store.</span></span> <span data-ttu-id="bb586-112">随后, 如果缓存的刷新间隔已过期, 则 .osc 不会调用**GetFriendsAndColleagues**或**GetDetails** 。</span><span class="sxs-lookup"><span data-stu-id="bb586-112">Subsequently the OSC does not call **GetFriendsAndColleagues** or **GetDetails** unless the refresh interval for the cache has expired.</span></span> <span data-ttu-id="bb586-113">有关 .osc 如何将朋友的信息缓存在联系人文件夹中的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="bb586-113">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb586-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb586-114">See also</span></span>

- [<span data-ttu-id="bb586-115">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bb586-115">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

