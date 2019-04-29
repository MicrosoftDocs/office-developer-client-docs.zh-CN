---
title: 活动的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: acc4a555-a3bf-4a79-86dc-aba6477733b8
description: 本主题包含一个示例方案, 显示了 .osc 提供商实施的 Outlook Social Connector (.osc) 提供程序扩展性 API 调用以及 .osc 获取活动信息的情况。 信息以符合 .osc 提供程序 XML 架构的 XML 字符串表示。
ms.openlocfilehash: a4f1c6ce1f33b59811f6a6fecb737cd1f737946b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409627"
---
# <a name="xml-for-activities"></a>活动的 XML

本主题包含一个示例方案, 显示了 .osc 提供商实施的 Outlook Social Connector (.osc) 提供程序扩展性 API 调用以及 .osc 获取活动信息的情况。 信息以符合 .osc 提供程序 XML 架构的 XML 字符串表示。
  
.osc 提供程序 XML 架构允许 .osc 提供程序定义活动。 活动信息可以包括生成活动源项目的社交网络、每个活动源项目的详细信息 (如活动的所有者、类型和发布日期) 以及用于显示该活动的模板。 若要支持在人员窗格或联系人卡片上显示活动, 社交网络的 .osc 提供程序必须实现并返回正确的活动 XML。 有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)。 有关同步朋友活动的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。 有关 .osc 提供程序 XML 架构的完整定义 (包括哪些元素是必需元素或可选的元素), 请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。 
  
在以下方案中, .osc 将动态同步在人员窗格中选择的人员的活动, 并获取有关该人员的详细信息:
  
1. 支持活动的按需同步的 .osc 提供程序指示通过使用**getActivities**和**dynamicActivitiesLookupEx**元素对 .osc 进行同步。 .osc 提供程序还设置了**hashFunction**元素。 所有三个元素都是**功能**的子元素。 
    
2. .osc 提供程序实现**ISocialProvider:: GetCapabilities**和[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 
    
3. .osc 调用**ISocialProvider:: GetCapabilities**检查**getActivities**和**dynamicActivitiesLookupEx**的值, 以验证 .osc 提供程序是否支持活动的按需同步。 该 .osc 还记录了 .osc 提供程序支持的**hashFunction**元素的值。 
    
4. .osc 刷新人员窗格或联系人卡片以让用户可以看到所选人员的最新活动。 .osc 通过使用**hashFunction**元素中指定的哈希函数来加密此人的 SMTP 地址, 形成符合**hashedAddresses**元素的 xml 架构定义的 xml 字符串。 
    
5. .osc 调用**ISocialSession2:: GetActivitiesEx**, 将哈希地址的 XML 字符串作为_hashedAddresses_参数提供, 以在_活动_参数中获取该人员的活动的当前集合。 _活动_参数字符串符合**microsoft.office.server.activityfeed**元素的 XML 架构定义。 
    
6. 根据**microsoft.office.server.activityfeed**的 XML 架构定义, .osc 会进一步分析_活动_字符串, 以了解有关每个活动的类型、发布日期和其他信息, 以及如何显示活动。 
    
7. 若要获取有关所选人员的详细信息, .osc 调用[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md), 将相同的哈希地址 XML 字符串提供为_personsAddresses_参数的参数。 有关人员的详细信息在_personsCollection_参数中返回。 这些详细信息可以包括**firstName**、 **lastName**和**emailAddress**。 _personsCollection_参数符合**person**元素的 XML 架构定义。 
    
您可以在本部分的以下主题中找到有关指定活动 XML 的详细信息:
  
- [活动源项目的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
- [正确显示活动的准则](guidelines-for-properly-displaying-activities.md)
    
## <a name="see-also"></a>另请参阅

- [活动源 XML 示例](activity-feed-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [XML 的功能](xml-for-capabilities.md)  
- [适用于好友的 XML](xml-for-friends.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

