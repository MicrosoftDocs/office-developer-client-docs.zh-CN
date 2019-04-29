---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: Outlook Social Connector (.osc) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素, 使其具有内存中的 .osc 存储活动项。
ms.openlocfilehash: b2fcaa125ac8bf7924726f4f09ff507769c3a3f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422913"
---
# <a name="guidelines-for-properly-displaying-activities"></a><span data-ttu-id="eee4d-103">有关正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="eee4d-103">Guidelines for properly displaying activities</span></span>

<span data-ttu-id="eee4d-104">Outlook Social Connector (.osc) 提供程序可以设置**getActivities**和**dynamicActivitiesLookupEx**元素, 使其具有内存中的 .osc 存储活动项。</span><span class="sxs-lookup"><span data-stu-id="eee4d-104">Outlook Social Connector (OSC) providers can set the **getActivities** and **dynamicActivitiesLookupEx** elements to have the OSC store activity items in memory.</span></span> <span data-ttu-id="eee4d-105">本主题介绍当 .osc 提供商支持从社交网络同步活动源时, .osc 调用以获取或刷新活动和活动所有者详细信息的 .osc 提供程序扩展性 api。</span><span class="sxs-lookup"><span data-stu-id="eee4d-105">This topic describes the OSC provider extensibility APIs that the OSC calls to get or refresh activities and activity owner details, if the OSC provider supports synchronizing activity feeds from the social network.</span></span> <span data-ttu-id="eee4d-106">本主题还列出了**microsoft.office.server.activityfeed**元素的一些子元素, .osc 提供程序应为 .osc 设置这些子元素, 以便在 Office 联系人卡片或 Outlook 人员窗格中正确显示活动。</span><span class="sxs-lookup"><span data-stu-id="eee4d-106">The topic also lists a few child elements of the **activityFeed** element that the OSC provider should set for the OSC to display activities properly in the Office Contact Card or Outlook People Pane.</span></span> 
  
- <span data-ttu-id="eee4d-107">.osc 调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法来获取和存储登录用户的 "新闻源" 文件夹中的活动。</span><span class="sxs-lookup"><span data-stu-id="eee4d-107">The OSC calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method to get and store activities in the News Feed folder for the logged-on user.</span></span> <span data-ttu-id="eee4d-108">.osc 提供程序必须实现**GetActivitiesEx** , 以返回符合**microsoft.office.server.activityfeed**元素的 .osc 提供程序 XML 架构定义的_活动_XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="eee4d-108">The OSC provider must implement **GetActivitiesEx** to return an  _activities_ XML string that complies with the OSC provider XML schema definition of the **activityFeed** element.</span></span> 
    
- <span data-ttu-id="eee4d-109">.osc 提供程序必须设置**ownerID**元素, 该元素是**activityDetails**元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="eee4d-109">The OSC provider must set the **ownerID** element, which is a child element of the **activityDetails** element.</span></span> <span data-ttu-id="eee4d-110">**ownerID**是一个不透明的字符串, 用于标识社交网络上活动的所有者。</span><span class="sxs-lookup"><span data-stu-id="eee4d-110">**ownerID** is an opaque string that identifies the owner of the activity on the social network.</span></span> 
    
- <span data-ttu-id="eee4d-111">.osc 提供程序应在**templateVariables**元素的**publisherVariable**节点中设置**nameHint**和**emailAddress**元素。</span><span class="sxs-lookup"><span data-stu-id="eee4d-111">The OSC provider should set the **nameHint** and **emailAddress** elements in the **publisherVariable** node of the **templateVariables** element.</span></span> 
    
   <span data-ttu-id="eee4d-112">请注意, 根据 .osc 提供程序 XML 架构, **nameHint**元素是可选元素。</span><span class="sxs-lookup"><span data-stu-id="eee4d-112">Note that per the OSC provider XML schema, the **nameHint** element is an optional element.</span></span> <span data-ttu-id="eee4d-113">.osc 使用它来匹配 "联系人卡片" 或 "人员" 窗格中所选用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="eee4d-113">The OSC uses it to match the display name of the user selected in the Contact Card or People Pane.</span></span> <span data-ttu-id="eee4d-114">同样, **emailAddress**元素是 XML 架构中的可选元素。</span><span class="sxs-lookup"><span data-stu-id="eee4d-114">Similarly, the **emailAddress** element is an optional element in the XML schema.</span></span> <span data-ttu-id="eee4d-115">.osc 使用它来匹配在联系人卡片或人员窗格中选择的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="eee4d-115">The OSC uses it to match the SMTP address of the user selected in the Contact Card or People Pane.</span></span> 
    
   <span data-ttu-id="eee4d-116">如果只指定了**ownerID**元素, 但未指定其中一个或两个**nameHint**和**emailAddress** , 则 .osc 将调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md)方法, 然后调用[ISocialPerson:: GetDetails](isocialperson-getdetails.md)方法, 以获取有关由**ownerID**标识的人员的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eee4d-116">If only the **ownerID** element is specified, but one or both of **nameHint** and **emailAddress** are not specified, the OSC calls the [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md) method and then the [ISocialPerson::GetDetails](isocialperson-getdetails.md) method to get more information about the person identified by the **ownerID**.</span></span> <span data-ttu-id="eee4d-117">当 .osc 调用**ISocialPerson:: GetDetails**时, 提供程序必须返回指定**fullName**和**emailAddress**元素的**人员**XML。</span><span class="sxs-lookup"><span data-stu-id="eee4d-117">When the OSC calls **ISocialPerson::GetDetails**, the provider must return **person** XML that specifies the **fullName** and **emailAddress** elements.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="eee4d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eee4d-118">See also</span></span>

- [<span data-ttu-id="eee4d-119">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="eee4d-119">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="eee4d-120">适用于好友的 XML</span><span class="sxs-lookup"><span data-stu-id="eee4d-120">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="eee4d-121">XML 的功能</span><span class="sxs-lookup"><span data-stu-id="eee4d-121">XML for Capabilities</span></span>](xml-for-capabilities.md)

