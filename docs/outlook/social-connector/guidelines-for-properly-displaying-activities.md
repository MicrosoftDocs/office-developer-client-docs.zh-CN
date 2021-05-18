---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: OutlookSOCIAL Connector (OSC) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素，以将 OSC 存储活动项到内存中。
ms.openlocfilehash: b2fcaa125ac8bf7924726f4f09ff507769c3a3f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422913"
---
# <a name="guidelines-for-properly-displaying-activities"></a><span data-ttu-id="16209-103">有关正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="16209-103">Guidelines for properly displaying activities</span></span>

<span data-ttu-id="16209-104">OutlookSOCIAL Connector (OSC) 提供程序可以设置 **getActivities** 和 **dynamicActivitiesLookupEx** 元素，以将 OSC 存储活动项内存中。</span><span class="sxs-lookup"><span data-stu-id="16209-104">Outlook Social Connector (OSC) providers can set the **getActivities** and **dynamicActivitiesLookupEx** elements to have the OSC store activity items in memory.</span></span> <span data-ttu-id="16209-105">本主题介绍 OSC 提供程序扩展性 API，如果 OSC 提供程序支持从社交网络同步活动源，则 OSC 将调用这些 API 获取或刷新活动和活动所有者详细信息。</span><span class="sxs-lookup"><span data-stu-id="16209-105">This topic describes the OSC provider extensibility APIs that the OSC calls to get or refresh activities and activity owner details, if the OSC provider supports synchronizing activity feeds from the social network.</span></span> <span data-ttu-id="16209-106">本主题还列出了 OSC 提供程序应为 OSC 设置的 **activityFeed** 元素的一些子元素，以在 Office 联系人卡片或联系人Outlook中正确显示活动。</span><span class="sxs-lookup"><span data-stu-id="16209-106">The topic also lists a few child elements of the **activityFeed** element that the OSC provider should set for the OSC to display activities properly in the Office Contact Card or Outlook People Pane.</span></span> 
  
- <span data-ttu-id="16209-107">OSC 调用 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法来获取活动，并存储登录用户的"新闻源"文件夹中的活动。</span><span class="sxs-lookup"><span data-stu-id="16209-107">The OSC calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method to get and store activities in the News Feed folder for the logged-on user.</span></span> <span data-ttu-id="16209-108">OSC 提供程序必须实现 **GetActivitiesEx** 以返回符合 **activityFeed** 元素的 OSC 提供程序 XML 架构定义的活动 _XML_ 字符串。</span><span class="sxs-lookup"><span data-stu-id="16209-108">The OSC provider must implement **GetActivitiesEx** to return an  _activities_ XML string that complies with the OSC provider XML schema definition of the **activityFeed** element.</span></span> 
    
- <span data-ttu-id="16209-109">OSC 提供程序必须设置 **ownerID** 元素，它是 **activityDetails 元素的子** 元素。</span><span class="sxs-lookup"><span data-stu-id="16209-109">The OSC provider must set the **ownerID** element, which is a child element of the **activityDetails** element.</span></span> <span data-ttu-id="16209-110">**ownerID** 是一个不透明字符串，用于标识社交网络上活动的所有者。</span><span class="sxs-lookup"><span data-stu-id="16209-110">**ownerID** is an opaque string that identifies the owner of the activity on the social network.</span></span> 
    
- <span data-ttu-id="16209-111">OSC 提供程序应在 **templateVariables** 元素的 **publisherVariable** 节点中设置 **nameHint** 和 **emailAddress** 元素。</span><span class="sxs-lookup"><span data-stu-id="16209-111">The OSC provider should set the **nameHint** and **emailAddress** elements in the **publisherVariable** node of the **templateVariables** element.</span></span> 
    
   <span data-ttu-id="16209-112">请注意，根据 OSC 提供程序 XML 架构 **，nameHint** 元素是可选元素。</span><span class="sxs-lookup"><span data-stu-id="16209-112">Note that per the OSC provider XML schema, the **nameHint** element is an optional element.</span></span> <span data-ttu-id="16209-113">OSC 使用它来匹配显示名称卡片或人员窗格中选择的用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="16209-113">The OSC uses it to match the display name of the user selected in the Contact Card or People Pane.</span></span> <span data-ttu-id="16209-114">同样 **，emailAddress** 元素是 XML 架构中的可选元素。</span><span class="sxs-lookup"><span data-stu-id="16209-114">Similarly, the **emailAddress** element is an optional element in the XML schema.</span></span> <span data-ttu-id="16209-115">OSC 使用它来匹配在联系人卡片或人员窗格中选择的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="16209-115">The OSC uses it to match the SMTP address of the user selected in the Contact Card or People Pane.</span></span> 
    
   <span data-ttu-id="16209-116">如果仅指定了 **ownerID** 元素，但未指定 **nameHint** 和 **emailAddress** 的一个或两个，则 OSC 将调用 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) 方法，然后调用 [ISocialPerson：：GetDetails](isocialperson-getdetails.md) 方法来获取有关 **ownerID** 标识的人详细信息。</span><span class="sxs-lookup"><span data-stu-id="16209-116">If only the **ownerID** element is specified, but one or both of **nameHint** and **emailAddress** are not specified, the OSC calls the [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md) method and then the [ISocialPerson::GetDetails](isocialperson-getdetails.md) method to get more information about the person identified by the **ownerID**.</span></span> <span data-ttu-id="16209-117">当 OSC 调用 **ISocialPerson：：GetDetails** 时，提供程序必须返回 **指定** **fullName** 和 **emailAddress** 元素的 person XML。</span><span class="sxs-lookup"><span data-stu-id="16209-117">When the OSC calls **ISocialPerson::GetDetails**, the provider must return **person** XML that specifies the **fullName** and **emailAddress** elements.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="16209-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16209-118">See also</span></span>

- [<span data-ttu-id="16209-119">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="16209-119">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="16209-120">好友 XML</span><span class="sxs-lookup"><span data-stu-id="16209-120">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="16209-121">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="16209-121">XML for Capabilities</span></span>](xml-for-capabilities.md)

