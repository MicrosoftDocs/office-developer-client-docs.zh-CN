---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串，表示详细信息的人员，如名字、 姓氏和一个 URL 为配置文件图片。
ms.openlocfilehash: 158ce9b5c6a97ffff0325427ed07c74f518941d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779208"
---
# <a name="isocialpersongetdetails"></a><span data-ttu-id="a643a-103">ISocialPerson::GetDetails</span><span class="sxs-lookup"><span data-stu-id="a643a-103">ISocialPerson::GetDetails</span></span>

<span data-ttu-id="a643a-104">获取一个字符串，表示详细信息的人员，如名字、 姓氏和一个 URL 为配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="a643a-104">Gets a string that represents details for the person, such as the first name, last name, and a URL to a profile picture.</span></span> 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a><span data-ttu-id="a643a-105">参数</span><span class="sxs-lookup"><span data-stu-id="a643a-105">Parameters</span></span>

<span data-ttu-id="a643a-106">_详细信息_</span><span class="sxs-lookup"><span data-stu-id="a643a-106">_details_</span></span>
  
> <span data-ttu-id="a643a-107">[输出]XML 字符串值，该值代表的人员的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a643a-107">[out] An XML string value that represents the details for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a643a-108">说明</span><span class="sxs-lookup"><span data-stu-id="a643a-108">Remarks</span></span>

<span data-ttu-id="a643a-109">Outlook Social Connector (OSC) 提供程序扩展性的架构中定义，返回的_详细信息_的 XML 字符串必须符合**人**，架构定义。</span><span class="sxs-lookup"><span data-stu-id="a643a-109">The returned  _details_ XML string must comply with the schema definition for **person**, as defined in the schema for Outlook Social Connector (OSC) provider extensibility.</span></span>
  
<span data-ttu-id="a643a-110">OSC 社交网络上调用**GetDetails**如果 OSC 提供程序支持缓存或朋友混合同步。</span><span class="sxs-lookup"><span data-stu-id="a643a-110">The OSC calls **GetDetails** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="a643a-111">当 OSC 最初获取在用户登录朋友的活动时，它调用[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)，并将朋友的信息存储中特定于登录的用户的默认 Outlook 存储区中的社交网络联系人文件夹.</span><span class="sxs-lookup"><span data-stu-id="a643a-111">When the OSC initially gets friends' activities for the logged on user, it calls [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), and stores friends' information in a contacts folder specific to the social network, in the logged on user's default Outlook store.</span></span> <span data-ttu-id="a643a-112">随后 OSC 不调用**GetFriendsAndColleagues**或**GetDetails**除非缓存刷新间隔时间已过期。</span><span class="sxs-lookup"><span data-stu-id="a643a-112">Subsequently the OSC does not call **GetFriendsAndColleagues** or **GetDetails** unless the refresh interval for the cache has expired.</span></span> <span data-ttu-id="a643a-113">有关如何 OSC 缓存联系人文件夹中的朋友的信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="a643a-113">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a643a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a643a-114">See also</span></span>

- [<span data-ttu-id="a643a-115">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a643a-115">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

