---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取表示人员集合的字符串。
ms.openlocfilehash: f755476f66ab2f91471b88c74baff899f31b83e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331659"
---
# <a name="isocialpersongetfriendsandcolleagues"></a><span data-ttu-id="ef334-103">ISocialPerson::GetFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="ef334-103">ISocialPerson::GetFriendsAndColleagues</span></span>

<span data-ttu-id="ef334-104">获取表示人员集合的字符串。</span><span class="sxs-lookup"><span data-stu-id="ef334-104">Gets a string that represents a collection of people.</span></span>
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="ef334-105">参数</span><span class="sxs-lookup"><span data-stu-id="ef334-105">Parameters</span></span>

<span data-ttu-id="ef334-106">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="ef334-106">_personsCollection_</span></span>
  
> <span data-ttu-id="ef334-107">排除一个 XML 字符串, 它表示人员的一组朋友, 并且符合 Outlook Social Connector (.osc) 提供程序可扩展性的 XML 架构中定义的**友元**定义。</span><span class="sxs-lookup"><span data-stu-id="ef334-107">[out] An XML string that represents a set of friends of the person, and that complies with the definition of **friends** as defined in the XML schema for Outlook Social Connector (OSC) provider extensibility.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ef334-108">注解</span><span class="sxs-lookup"><span data-stu-id="ef334-108">Remarks</span></span>

<span data-ttu-id="ef334-109">如果 .osc 提供商支持社交网络上的友元缓存或混合同步, 则 .osc 调用**GetFriendsAndColleagues** 。</span><span class="sxs-lookup"><span data-stu-id="ef334-109">The OSC calls **GetFriendsAndColleagues** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="ef334-110">当 .osc 最初调用登录到社交网络的 Outlook 用户的**GetFriendsAndColleagues**方法时, **GetFriendsAndColleagues**将返回一个代表社交网络上登录用户的好友的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="ef334-110">When the OSC initially calls the **GetFriendsAndColleagues** method for the Outlook user who is logged on to the social network, **GetFriendsAndColleagues** returns an XML string that represents friends of the logged-on user on the social network.</span></span> <span data-ttu-id="ef334-111">XML 字符串符合**好友**XML 架构定义, 并指定每个好友的**person**元素 (也符合 .osc 提供程序架构定义)。</span><span class="sxs-lookup"><span data-stu-id="ef334-111">The XML string complies with the **friends** XML schema definition and specifies a **person** element (which also complies with the OSC provider schema definition) for each friend.</span></span> 
  
<span data-ttu-id="ef334-112">当**GetFriendsAndColleagues**返回已登录用户的好友信息时, .osc 会将该信息存储在 "联系人" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ef334-112">When **GetFriendsAndColleagues** returns the friends information for the logged-on user, the OSC stores that information in a contacts folder.</span></span> <span data-ttu-id="ef334-113">此文件夹特定于社交网络, 并驻留在登录用户的默认 Outlook 存储中。</span><span class="sxs-lookup"><span data-stu-id="ef334-113">This folder is specific to the social network and resides in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="ef334-114">有关 .osc 如何将朋友的信息缓存在联系人文件夹中的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="ef334-114">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="ef334-115">_personsCollection_参数中返回的每个友元的信息符合**人员**的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="ef334-115">Information for each friend returned in the  _personsCollection_ parameter complies with the XML schema definition for **person**.</span></span> <span data-ttu-id="ef334-116">**person**元素支持每个好友的多条信息, 包括 SMTP 电子邮件地址 (映射到好友在其上指定的**emailAddress**、 **emailAddress2**和**emailAddress3**元素)社交网络, 以及在社交网络上标识该好友的用户 ID (映射到**userID**元素)。</span><span class="sxs-lookup"><span data-stu-id="ef334-116">The **person** element supports many pieces of information for each friend, including the SMTP email addresses (which map to the **emailAddress**, **emailAddress2**, and **emailAddress3** elements) that the friend has specified on the social network, and the user ID (which maps to the **userID** element) that identifies that friend on the social network.</span></span> 
  
<span data-ttu-id="ef334-117">若要显示在 "人员" 窗格中选定的 Outlook 用户的活动, .osc 将尝试使用户与从**GetFriendsAndColleagues**返回的每个朋友相匹配。</span><span class="sxs-lookup"><span data-stu-id="ef334-117">To show activities for an Outlook user selected in the People Pane, the OSC tries to match the user with each friend returned from **GetFriendsAndColleagues**.</span></span> <span data-ttu-id="ef334-118">通过将所选 Outlook 用户的 SMTP 地址与每个好友在社交网络中指定的电子邮件地址相匹配, .osc 实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ef334-118">The OSC does this by matching the SMTP address of the selected Outlook user with the email addresses that each friend has specified on the social network.</span></span> <span data-ttu-id="ef334-119">如果 .osc 找到匹配的 SMTP 电子邮件地址, 则 .osc 将使用友元的相应**用户 id**调用[ISocialSession:: GetPerson](isocialsession-getperson.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ef334-119">If the OSC finds a matching SMTP email address, the OSC uses the corresponding **userID** of the friend to call the [ISocialSession::GetPerson](isocialsession-getperson.md) method.</span></span> <span data-ttu-id="ef334-120">它将执行此操作以获取该好友的[ISocialPerson](isocialpersoniunknown.md)对象, 该对象随后使 .osc 能够从社交网络中获取该朋友的活动和图片。</span><span class="sxs-lookup"><span data-stu-id="ef334-120">It does this to obtain an [ISocialPerson](isocialpersoniunknown.md) object for that friend, which then enables the OSC to get activities and pictures of that friend from the social network.</span></span> 
  
<span data-ttu-id="ef334-121">但是, 如果所选的 Outlook 用户未在社交网络上的帐户上指定相同的 SMTP 地址, 或者如果 outlook 用户在社交网络上没有帐户, 则该 .osc 将无法找到该用户的匹配项, 并且不会显示任何 activiti社交网络上该用户的 es。</span><span class="sxs-lookup"><span data-stu-id="ef334-121">However, if the selected Outlook user does not specify that same SMTP address on an account on the social network, or if the Outlook user does not have an account on that social network, the OSC will not be able to find a match for that user and will not display any activities for that user on the social network.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef334-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef334-122">See also</span></span>

- [<span data-ttu-id="ef334-123">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ef334-123">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)
- [<span data-ttu-id="ef334-124">获取好友信息</span><span class="sxs-lookup"><span data-stu-id="ef334-124">Getting Friends Information</span></span>](getting-friends-information.md)

