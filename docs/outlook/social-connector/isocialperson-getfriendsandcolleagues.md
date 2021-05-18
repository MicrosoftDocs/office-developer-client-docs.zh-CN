---
title: ISocialPersonGetFriendsAndColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62d5b815-f199-499e-85eb-2dff21a8216e
description: 获取一个代表人员集合的字符串。
ms.openlocfilehash: f755476f66ab2f91471b88c74baff899f31b83e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407653"
---
# <a name="isocialpersongetfriendsandcolleagues"></a><span data-ttu-id="1e4ce-103">ISocialPerson::GetFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="1e4ce-103">ISocialPerson::GetFriendsAndColleagues</span></span>

<span data-ttu-id="1e4ce-104">获取一个代表人员集合的字符串。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-104">Gets a string that represents a collection of people.</span></span>
  
```cpp
HRESULT _stdcall GetFriendsAndColleagues([out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="1e4ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e4ce-105">Parameters</span></span>

<span data-ttu-id="1e4ce-106">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="1e4ce-106">_personsCollection_</span></span>
  
> <span data-ttu-id="1e4ce-107">[out]一个 XML 字符串，表示一组好友，并且符合 OUTLOOK Social Connector  (OSC 提供程序扩展的 XML 架构中定义的好友) 定义。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-107">[out] An XML string that represents a set of friends of the person, and that complies with the definition of **friends** as defined in the XML schema for Outlook Social Connector (OSC) provider extensibility.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1e4ce-108">备注</span><span class="sxs-lookup"><span data-stu-id="1e4ce-108">Remarks</span></span>

<span data-ttu-id="1e4ce-109">如果 OSC 提供程序支持社交网络上好友的缓存或混合同步，OSC 将调用 **GetFriendsAndColleagues。**</span><span class="sxs-lookup"><span data-stu-id="1e4ce-109">The OSC calls **GetFriendsAndColleagues** if the OSC provider supports cached or hybrid synchronization of friends on the social network.</span></span> <span data-ttu-id="1e4ce-110">当 OSC 最初为登录到社交网络的 Outlook 用户调用 **GetFriendsAndColleagues** 方法时 **，GetFriendsAndColleagues** 将返回一个 XML 字符串，该字符串表示社交网络上已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-110">When the OSC initially calls the **GetFriendsAndColleagues** method for the Outlook user who is logged on to the social network, **GetFriendsAndColleagues** returns an XML string that represents friends of the logged-on user on the social network.</span></span> <span data-ttu-id="1e4ce-111">XML 字符串符合 **好友** XML 架构定义，并指定 **person** 元素 (该元素还符合每个好友的 OSC 提供程序架构) 定义。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-111">The XML string complies with the **friends** XML schema definition and specifies a **person** element (which also complies with the OSC provider schema definition) for each friend.</span></span> 
  
<span data-ttu-id="1e4ce-112">当 **GetFriendsAndColleagues** 返回已登录用户的好友信息时，OSC 将该信息存储在联系人文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-112">When **GetFriendsAndColleagues** returns the friends information for the logged-on user, the OSC stores that information in a contacts folder.</span></span> <span data-ttu-id="1e4ce-113">此文件夹特定于社交网络，并驻留在登录用户的默认Outlook存储中。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-113">This folder is specific to the social network and resides in the logged-on user's default Outlook store.</span></span> <span data-ttu-id="1e4ce-114">有关 OSC 如何在联系人文件夹中缓存好友信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-114">For more information about how the OSC caches friends' information in a contacts folder, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
<span data-ttu-id="1e4ce-115">_personCollection_ 参数中返回的每个好友的信息都符合 person 的 XML 架构 **定义**。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-115">Information for each friend returned in the  _personsCollection_ parameter complies with the XML schema definition for **person**.</span></span> <span data-ttu-id="1e4ce-116">**person** 元素支持每个好友的许多信息，包括映射到好友在社交网络上指定的 **emailAddress、emailAddress2** 和 **emailAddress3** 元素) 的 SMTP 电子邮件地址 (以及映射到标识社交网络上该好友的 **userID** 元素) 的用户 ID (。 </span><span class="sxs-lookup"><span data-stu-id="1e4ce-116">The **person** element supports many pieces of information for each friend, including the SMTP email addresses (which map to the **emailAddress**, **emailAddress2**, and **emailAddress3** elements) that the friend has specified on the social network, and the user ID (which maps to the **userID** element) that identifies that friend on the social network.</span></span> 
  
<span data-ttu-id="1e4ce-117">若要显示用户在人员Outlook选择的活动，OSC 会尝试将该用户与从 **GetFriendsAndColleagues** 返回的每个好友匹配。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-117">To show activities for an Outlook user selected in the People Pane, the OSC tries to match the user with each friend returned from **GetFriendsAndColleagues**.</span></span> <span data-ttu-id="1e4ce-118">OSC 通过匹配所选用户的 SMTP 地址Outlook每个好友在社交网络上指定的电子邮件地址来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-118">The OSC does this by matching the SMTP address of the selected Outlook user with the email addresses that each friend has specified on the social network.</span></span> <span data-ttu-id="1e4ce-119">如果 OSC 找到匹配的 SMTP 电子邮件地址，OSC 将使用好友的相应 **userID** 调用 [ISocialSession：：GetPerson](isocialsession-getperson.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-119">If the OSC finds a matching SMTP email address, the OSC uses the corresponding **userID** of the friend to call the [ISocialSession::GetPerson](isocialsession-getperson.md) method.</span></span> <span data-ttu-id="1e4ce-120">它执行此操作以获取该好友的 [ISocialPerson](isocialpersoniunknown.md) 对象，然后 OSC 通过该对象从社交网络获取该好友的活动和图片。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-120">It does this to obtain an [ISocialPerson](isocialpersoniunknown.md) object for that friend, which then enables the OSC to get activities and pictures of that friend from the social network.</span></span> 
  
<span data-ttu-id="1e4ce-121">但是，如果所选的 Outlook 用户未在社交网络上的帐户上指定同一 SMTP 地址，或者 Outlook 用户没有该社交网络上的帐户，则 OSC 将无法找到该用户的匹配项，并且不会在社交网络上显示该用户的任何活动。</span><span class="sxs-lookup"><span data-stu-id="1e4ce-121">However, if the selected Outlook user does not specify that same SMTP address on an account on the social network, or if the Outlook user does not have an account on that social network, the OSC will not be able to find a match for that user and will not display any activities for that user on the social network.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e4ce-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e4ce-122">See also</span></span>

- [<span data-ttu-id="1e4ce-123">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1e4ce-123">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)
- [<span data-ttu-id="1e4ce-124">获取好友信息</span><span class="sxs-lookup"><span data-stu-id="1e4ce-124">Getting Friends Information</span></span>](getting-friends-information.md)

