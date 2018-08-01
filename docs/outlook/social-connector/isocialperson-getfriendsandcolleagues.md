---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取一个字符串，表示的人员的集合。
ms.openlocfilehash: 36482a6068c592eb0ff07603b6458e8415c3586f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779217"
---
# <a name="isocialpersongetfriendsandcolleagues"></a><span data-ttu-id="4dc06-103">ISocialPerson::GetFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="4dc06-103">ISocialPerson::GetFriendsAndColleagues</span></span>

<span data-ttu-id="4dc06-104">获取一个字符串，表示的人员的集合。</span><span class="sxs-lookup"><span data-stu-id="4dc06-104">Gets a string that represents a collection of people.</span></span>
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="4dc06-105">参数</span><span class="sxs-lookup"><span data-stu-id="4dc06-105">Parameters</span></span>

<span data-ttu-id="4dc06-106">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="4dc06-106">_personsCollection_</span></span>
  
> <span data-ttu-id="4dc06-107">[输出]表示一的人员，朋友和的符合**朋友**的定义中的 Outlook Social Connector (OSC) 提供程序扩展性的 XML 架构定义一个 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="4dc06-107">[out] An XML string that represents a set of friends of the person, and that complies with the definition of **friends** as defined in the XML schema for Outlook Social Connector (OSC) provider extensibility.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4dc06-108">说明</span><span class="sxs-lookup"><span data-stu-id="4dc06-108">Remarks</span></span>

<span data-ttu-id="4dc06-109">OSC 社交网络上调用**GetFriendsAndColleagues**如果 OSC 提供程序支持缓存或朋友混合同步。</span><span class="sxs-lookup"><span data-stu-id="4dc06-109">The OSC calls **GetFriendsAndColleagues** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="4dc06-110">当 OSC 最初**GetFriendsAndColleagues**为调用方法的 Outlook 用户的登录到社交网络， **GetFriendsAndColleagues**返回 XML 字符串值，该值代表登录用户的社交网络的朋友。</span><span class="sxs-lookup"><span data-stu-id="4dc06-110">When the OSC initially calls the **GetFriendsAndColleagues** method for the Outlook user who is logged on to the social network, **GetFriendsAndColleagues** returns an XML string that represents friends of the logged-on user on the social network.</span></span> <span data-ttu-id="4dc06-111">XML 字符串符合**朋友**XML 架构定义，并为每个朋友指定**人员**元素 （其还符合 OSC 提供程序架构定义）。</span><span class="sxs-lookup"><span data-stu-id="4dc06-111">The XML string complies with the **friends** XML schema definition and specifies a **person** element (which also complies with the OSC provider schema definition) for each friend.</span></span> 
  
<span data-ttu-id="4dc06-112">**GetFriendsAndColleagues**返回朋友登录用户的信息，OSC 将该信息存储在联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4dc06-112">When **GetFriendsAndColleagues** returns the friends information for the logged-on user, the OSC stores that information in a contacts folder.</span></span> <span data-ttu-id="4dc06-113">此文件夹特定于社交网络和驻留在登录用户的默认 Outlook 存储区。</span><span class="sxs-lookup"><span data-stu-id="4dc06-113">This folder is specific to the social network and resides in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="4dc06-114">有关如何 OSC 缓存联系人文件夹中的朋友的信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc06-114">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="4dc06-115">返回_personsCollection_参数中每个朋友信息符合**人**的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="4dc06-115">Information for each friend returned in the  _personsCollection_ parameter complies with the XML schema definition for **person**.</span></span> <span data-ttu-id="4dc06-116">**Person**元素支持每个朋友，包括的 SMTP 电子邮件地址 （其映射到的**电子邮件地址**、 **emailAddress2**和**emailAddress3**元素） 的信息的许多部分朋友具有在指定社交网络和用户 ID （其映射到**userID**元素），标识社交网络上的好帮手。</span><span class="sxs-lookup"><span data-stu-id="4dc06-116">The **person** element supports many pieces of information for each friend, including the SMTP email addresses (which map to the **emailAddress**, **emailAddress2**, and **emailAddress3** elements) that the friend has specified on the social network, and the user ID (which maps to the **userID** element) that identifies that friend on the social network.</span></span> 
  
<span data-ttu-id="4dc06-117">若要显示在人员窗格中选择的 Outlook 用户的活动，OSC 尝试与从**GetFriendsAndColleagues**返回每个朋友相匹配用户。</span><span class="sxs-lookup"><span data-stu-id="4dc06-117">To show activities for an Outlook user selected in the People Pane, the OSC tries to match the user with each friend returned from **GetFriendsAndColleagues**.</span></span> <span data-ttu-id="4dc06-118">OSC 匹配所选的 Outlook 用户的 SMTP 地址，每个朋友具有指定社交网络的电子邮件地址来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="4dc06-118">The OSC does this by matching the SMTP address of the selected Outlook user with the email addresses that each friend has specified on the social network.</span></span> <span data-ttu-id="4dc06-119">如果 OSC 找到匹配的 SMTP 电子邮件地址，OSC 使用朋友相应**userID**调用[ISocialSession::GetPerson](isocialsession-getperson.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4dc06-119">If the OSC finds a matching SMTP email address, the OSC uses the corresponding **userID** of the friend to call the [ISocialSession::GetPerson](isocialsession-getperson.md) method.</span></span> <span data-ttu-id="4dc06-120">它这样做是为了获取该朋友，然后使 OSC 以获得社交网络活动和该朋友的图片[ISocialPerson](isocialpersoniunknown.md)对象。</span><span class="sxs-lookup"><span data-stu-id="4dc06-120">It does this to obtain an [ISocialPerson](isocialpersoniunknown.md) object for that friend, which then enables the OSC to get activities and pictures of that friend from the social network.</span></span> 
  
<span data-ttu-id="4dc06-121">但是，如果所选的 Outlook 用户没有帐户的社交网络上指定的相同的 SMTP 地址或 Outlook 用户不具有该社交网络上的帐户，则 OSC 将不能以查找该用户的匹配并且不会显示任何 activities 社交网络上的用户。</span><span class="sxs-lookup"><span data-stu-id="4dc06-121">However, if the selected Outlook user does not specify that same SMTP address on an account on the social network, or if the Outlook user does not have an account on that social network, the OSC will not be able to find a match for that user and will not display any activities for that user on the social network.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4dc06-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc06-122">See also</span></span>

- [<span data-ttu-id="4dc06-123">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4dc06-123">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)
- [<span data-ttu-id="4dc06-124">获取好友信息</span><span class="sxs-lookup"><span data-stu-id="4dc06-124">Getting Friends Information</span></span>](getting-friends-information.md)

