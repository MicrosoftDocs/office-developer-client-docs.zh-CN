---
title: 有关正确显示活动的指南
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 55268188-8432-4145-9527-f5888949fc24
description: Outlook Social Connector (OSC) 提供程序可以设置 getActivities 和 dynamicActivitiesLookupEx 元素具有 OSC 存储在内存中的活动项目。
ms.openlocfilehash: f8cb5850c8920f09f784343db18372bb75ca17a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779200"
---
# <a name="guidelines-for-properly-displaying-activities"></a><span data-ttu-id="48b78-103">有关正确显示活动的指南</span><span class="sxs-lookup"><span data-stu-id="48b78-103">Guidelines for properly displaying activities</span></span>

<span data-ttu-id="48b78-104">Outlook Social Connector (OSC) 提供程序可以设置**getActivities**和**dynamicActivitiesLookupEx**元素具有 OSC 存储在内存中的活动项目。</span><span class="sxs-lookup"><span data-stu-id="48b78-104">Outlook Social Connector (OSC) providers can set the **getActivities** and **dynamicActivitiesLookupEx** elements to have the OSC store activity items in memory.</span></span> <span data-ttu-id="48b78-105">本主题介绍 Api OSC 调用来获取或刷新活动和活动所有者详细信息，如果 OSC 提供程序支持同步活动源与社交网络 OSC 提供程序扩展性。</span><span class="sxs-lookup"><span data-stu-id="48b78-105">This topic describes the OSC provider extensibility APIs that the OSC calls to get or refresh activities and activity owner details, if the OSC provider supports synchronizing activity feeds from the social network.</span></span> <span data-ttu-id="48b78-106">主题还列出了为 OSC 提供程序无法正常显示活动，在 Office 联系人卡片或 Outlook 人员窗格 OSC **activityFeed**元素的一些子元素。</span><span class="sxs-lookup"><span data-stu-id="48b78-106">The topic also lists a few child elements of the **activityFeed** element that the OSC provider should set for the OSC to display activities properly in the Office Contact Card or Outlook People Pane.</span></span> 
  
- <span data-ttu-id="48b78-107">OSC 调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法获取和登录用户的新闻源文件夹中存储活动。</span><span class="sxs-lookup"><span data-stu-id="48b78-107">The OSC calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method to get and store activities in the News Feed folder for the logged-on user.</span></span> <span data-ttu-id="48b78-108">OSC 提供程序必须实现**GetActivitiesEx**返回符合 OSC 提供程序**activityFeed**元素的 XML 架构定义一个_活动_XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="48b78-108">The OSC provider must implement **GetActivitiesEx** to return an  _activities_ XML string that complies with the OSC provider XML schema definition of the **activityFeed** element.</span></span> 
    
- <span data-ttu-id="48b78-109">OSC 提供程序必须设置**ownerID**元素，它是**activityDetails**元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="48b78-109">The OSC provider must set the **ownerID** element, which is a child element of the **activityDetails** element.</span></span> <span data-ttu-id="48b78-110">**ownerID**是活动的不透明字符串，标识社交网络上的所有者。</span><span class="sxs-lookup"><span data-stu-id="48b78-110">**ownerID** is an opaque string that identifies the owner of the activity on the social network.</span></span> 
    
- <span data-ttu-id="48b78-111">OSC 提供程序应在**templateVariables**元素的**publisherVariable**节点中设置的**nameHint**和**emailAddress**元素。</span><span class="sxs-lookup"><span data-stu-id="48b78-111">The OSC provider should set the **nameHint** and **emailAddress** elements in the **publisherVariable** node of the **templateVariables** element.</span></span> 
    
   <span data-ttu-id="48b78-112">请注意，每个 OSC 提供程序 XML 架构， **nameHint**元素是可选的元素。</span><span class="sxs-lookup"><span data-stu-id="48b78-112">Note that per the OSC provider XML schema, the **nameHint** element is an optional element.</span></span> <span data-ttu-id="48b78-113">OSC 使用它来匹配的联系人卡片或人员窗格中选定的用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="48b78-113">The OSC uses it to match the display name of the user selected in the Contact Card or People Pane.</span></span> <span data-ttu-id="48b78-114">同样， **emailAddress**元素是可选的 XML 架构中元素。</span><span class="sxs-lookup"><span data-stu-id="48b78-114">Similarly, the **emailAddress** element is an optional element in the XML schema.</span></span> <span data-ttu-id="48b78-115">OSC 使用它来匹配的联系人卡片或人员窗格中选定的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="48b78-115">The OSC uses it to match the SMTP address of the user selected in the Contact Card or People Pane.</span></span> 
    
   <span data-ttu-id="48b78-116">如果只指定**ownerID**元素，但未指定一个或两个**nameHint**和**电子邮件地址**，OSC 调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)方法然后[ISocialPerson::GetDetails](isocialperson-getdetails.md)若要获取有关由**ownerID**标识的人员的详细信息的方法。</span><span class="sxs-lookup"><span data-stu-id="48b78-116">If only the **ownerID** element is specified, but one or both of **nameHint** and **emailAddress** are not specified, the OSC calls the [ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md) method and then the [ISocialPerson::GetDetails](isocialperson-getdetails.md) method to get more information about the person identified by the **ownerID**.</span></span> <span data-ttu-id="48b78-117">当 OSC 调用**ISocialPerson::GetDetails**时，提供程序必须返回**人**指定的**全名**和**emailAddress**元素的 XML。</span><span class="sxs-lookup"><span data-stu-id="48b78-117">When the OSC calls **ISocialPerson::GetDetails**, the provider must return **person** XML that specifies the **fullName** and **emailAddress** elements.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="48b78-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48b78-118">See also</span></span>

- [<span data-ttu-id="48b78-119">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="48b78-119">XML for Activities</span></span>](xml-for-activities.md)  
- [<span data-ttu-id="48b78-120">朋友 XML</span><span class="sxs-lookup"><span data-stu-id="48b78-120">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="48b78-121">功能 XML</span><span class="sxs-lookup"><span data-stu-id="48b78-121">XML for Capabilities</span></span>](xml-for-capabilities.md)

