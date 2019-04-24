---
title: 获取好友信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8a56746-4de4-4f24-af32-e85079c060b8
description: 'Outlook Social Connector (.osc) 调用 ISocialProvider:: GetCapabilities 方法来确定用于社交网络的 .osc 提供程序的功能。'
ms.openlocfilehash: 697902631b010afab015e9cfb73fac81ac427d6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286320"
---
# <a name="getting-friends-information"></a><span data-ttu-id="6e0fd-103">获取好友信息</span><span class="sxs-lookup"><span data-stu-id="6e0fd-103">Getting friends information</span></span>

<span data-ttu-id="6e0fd-104">Outlook Social Connector (.osc) 调用[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法来确定用于社交网络的 .osc 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-104">The Outlook Social Connector (OSC) calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="6e0fd-105">如果返回的**功能**XML 中的**getFriends**和**cacheFriends**元素指示 .osc 提供程序支持将好友作为 Outlook 联系人项目放在相应的 "联系人" 文件夹中, 则 .osc 可以进行以下调用序列。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-105">If the **getFriends** and **cacheFriends** elements in the returned **capabilities** XML indicate that the OSC provider supports getting friends and caching friends as Outlook contact items in a corresponding contacts folder, the OSC can make the following calling sequence.</span></span> <span data-ttu-id="6e0fd-106">.osc 调用此序列中的方法, 以获取社交网络上的好友的信息和图片 (由[ISocialPerson](isocialpersoniunknown.md)接口支持)。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-106">The OSC calls methods in this sequence to get information and pictures (as supported by the [ISocialPerson](isocialpersoniunknown.md) interface) for friends on the social network.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6e0fd-107">.osc 将以默认间隔刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-107">The OSC refreshes the cache at a default interval.</span></span> <span data-ttu-id="6e0fd-108">如果在缓存刷新期间发生错误, 则在其他预设间隔内进行的 .osc 重试, 也可以通过在**功能**XML 中指定**contactSyncRestartInterval**元素来对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-108">If an error occurs during cache refresh, the OSC retries at another preset interval, which can also be controlled by specifying the **contactSyncRestartInterval** element in the **capabilities** XML.</span></span> <span data-ttu-id="6e0fd-109">有关刷新联系人缓存的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-109">For more information about refreshing the contacts cache, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
1. <span data-ttu-id="6e0fd-110">[ISocialSession:: LoggedOnUserID](isocialsession-loggedonuserid.md) — .osc 获取登录到社交网络的 Office 用户的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-110">[ISocialSession::LoggedOnUserID](isocialsession-loggedonuserid.md) —The OSC gets the user ID of the Office user who is logged onto the social network.</span></span> 
    
2. <span data-ttu-id="6e0fd-111">[ISocialSession:: GetPerson](isocialsession-getperson.md) —使用 Office 用户的用户 ID, .osc 获取该用户的**ISocialPerson**对象。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-111">[ISocialSession::GetPerson](isocialsession-getperson.md) —Using the user ID of the Office user, the OSC gets an **ISocialPerson** object for that user.</span></span> 
    
3. <span data-ttu-id="6e0fd-112">[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) — .osc 获取社交网络上的用户的友元列表。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-112">[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) —The OSC gets the user's friend list on the social network.</span></span> 
    
4. <span data-ttu-id="6e0fd-113">[ISocialSession:: GetPerson](isocialsession-getperson.md) -对于**GetFriendsAndColleagues**返回的 XML 中的每个人, .osc 获取一个**ISocialPerson**接口。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-113">[ISocialSession::GetPerson](isocialsession-getperson.md) —For each person in the XML returned by **GetFriendsAndColleagues**, the OSC gets an **ISocialPerson** interface.</span></span> 
    
5. <span data-ttu-id="6e0fd-114">[ISocialPerson:: GetPicture](isocialperson-getpicture.md) -对于**GetFriendsAndColleagues**返回的 XML 中的每个人, .osc 获取图片资源。</span><span class="sxs-lookup"><span data-stu-id="6e0fd-114">[ISocialPerson::GetPicture](isocialperson-getpicture.md) —For each person in the XML returned by **GetFriendsAndColleagues**, the OSC gets a picture resource.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6e0fd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e0fd-115">See also</span></span>

- [<span data-ttu-id="6e0fd-116">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="6e0fd-116">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="6e0fd-117">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="6e0fd-117">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

