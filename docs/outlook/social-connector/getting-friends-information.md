---
title: 获取好友信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8a56746-4de4-4f24-af32-e85079c060b8
description: Outlook Social Connector (OSC) 调用 ISocialProvider::GetCapabilities 方法来确定社交网络 OSC 提供程序的功能。
ms.openlocfilehash: 68443992351f4c83e8e560a753941e97bf91de67
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779198"
---
# <a name="getting-friends-information"></a><span data-ttu-id="c23d3-103">获取好友信息</span><span class="sxs-lookup"><span data-stu-id="c23d3-103">Getting friends information</span></span>

<span data-ttu-id="c23d3-104">Outlook Social Connector (OSC) 调用[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法来确定社交网络 OSC 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="c23d3-104">The Outlook Social Connector (OSC) calls the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method to determine the capabilities of the OSC provider for a social network.</span></span> <span data-ttu-id="c23d3-105">如果返回**功能**XML 中的**getFriends**和**cacheFriends**元素指示 OSC 提供程序支持入门朋友和缓存朋友作为 Outlook 联系人项目对应的联系人文件夹中，可以使 OSC下面的调用序列。</span><span class="sxs-lookup"><span data-stu-id="c23d3-105">If the **getFriends** and **cacheFriends** elements in the returned **capabilities** XML indicate that the OSC provider supports getting friends and caching friends as Outlook contact items in a corresponding contacts folder, the OSC can make the following calling sequence.</span></span> <span data-ttu-id="c23d3-106">OSC 按此顺序获得信息和图片 （如[ISocialPerson](isocialpersoniunknown.md)接口支持） 的社交网络上的朋友调用方法。</span><span class="sxs-lookup"><span data-stu-id="c23d3-106">The OSC calls methods in this sequence to get information and pictures (as supported by the [ISocialPerson](isocialpersoniunknown.md) interface) for friends on the social network.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c23d3-107">OSC 刷新按默认的时间间隔的缓存。</span><span class="sxs-lookup"><span data-stu-id="c23d3-107">The OSC refreshes the cache at a default interval.</span></span> <span data-ttu-id="c23d3-108">如果缓存期间发生错误刷新，在另一个预设的间隔，也可以通过在**功能**XML 中指定的**contactSyncRestartInterval**元素控制 OSC 重试。</span><span class="sxs-lookup"><span data-stu-id="c23d3-108">If an error occurs during cache refresh, the OSC retries at another preset interval, which can also be controlled by specifying the **contactSyncRestartInterval** element in the **capabilities** XML.</span></span> <span data-ttu-id="c23d3-109">有关刷新联系人缓存的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="c23d3-109">For more information about refreshing the contacts cache, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span> 
  
1. <span data-ttu-id="c23d3-110">[ISocialSession::LoggedOnUserID](isocialsession-loggedonuserid.md) — OSC 获取 Office 用户登录到社交网络的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="c23d3-110">[ISocialSession::LoggedOnUserID](isocialsession-loggedonuserid.md) —The OSC gets the user ID of the Office user who is logged onto the social network.</span></span> 
    
2. <span data-ttu-id="c23d3-111">[ISocialSession::GetPerson](isocialsession-getperson.md) — 使用 Office 用户的用户 ID，OSC 该用户的中获取**ISocialPerson**对象。</span><span class="sxs-lookup"><span data-stu-id="c23d3-111">[ISocialSession::GetPerson](isocialsession-getperson.md) —Using the user ID of the Office user, the OSC gets an **ISocialPerson** object for that user.</span></span> 
    
3. <span data-ttu-id="c23d3-112">[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) — OSC 社交网络上获取用户的好朋友列表。</span><span class="sxs-lookup"><span data-stu-id="c23d3-112">[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) —The OSC gets the user's friend list on the social network.</span></span> 
    
4. <span data-ttu-id="c23d3-113">[ISocialSession::GetPerson](isocialsession-getperson.md) — OSC 的 XML 中的每个人，则由**GetFriendsAndColleagues**返回，获取**ISocialPerson**接口。</span><span class="sxs-lookup"><span data-stu-id="c23d3-113">[ISocialSession::GetPerson](isocialsession-getperson.md) —For each person in the XML returned by **GetFriendsAndColleagues**, the OSC gets an **ISocialPerson** interface.</span></span> 
    
5. <span data-ttu-id="c23d3-114">[ISocialPerson::GetPicture](isocialperson-getpicture.md) — OSC 的 XML 中的每个人，则由**GetFriendsAndColleagues**返回，获取图片的资源。</span><span class="sxs-lookup"><span data-stu-id="c23d3-114">[ISocialPerson::GetPicture](isocialperson-getpicture.md) —For each person in the XML returned by **GetFriendsAndColleagues**, the OSC gets a picture resource.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c23d3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c23d3-115">See also</span></span>

- [<span data-ttu-id="c23d3-116">功能 XML</span><span class="sxs-lookup"><span data-stu-id="c23d3-116">XML for Capabilities</span></span>](xml-for-capabilities.md)
- [<span data-ttu-id="c23d3-117">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="c23d3-117">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)

