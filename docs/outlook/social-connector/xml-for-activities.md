---
title: 活动的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: acc4a555-a3bf-4a79-86dc-aba6477733b8
description: 本主题包含显示 Outlook Social Connector (OSC) 提供程序扩展性 API 调用 OSC 提供程序实现和 OSC 使获取活动信息的示例方案。 符合 OSC 提供程序的 XML 架构的 XML 字符串中表示的信息。
ms.openlocfilehash: 44f74d9e72eec3ff6da7f9967315fc9d75191584
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779344"
---
# <a name="xml-for-activities"></a>活动的 XML

本主题包含显示 Outlook Social Connector (OSC) 提供程序扩展性 API 调用 OSC 提供程序实现和 OSC 使获取活动信息的示例方案。 符合 OSC 提供程序的 XML 架构的 XML 字符串中表示的信息。
  
OSC 提供程序 XML 架构允许 OSC 提供程序定义活动。 活动信息可以包含其中活动源项目产生，社交网络的每个活动源项目详细信息 （如所有者，键入，和活动的发布日期），并显示活动的模板。 若要支持人员窗格或联系人卡片上显示活动，社交网络的 OSC 提供程序必须实现并返回正确的活动 XML。 示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)。 有关同步朋友的活动的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。 有关完整定义 OSC 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。 
  
在以下方案中，OSC 动态活动同步人员窗格中选择联系人，并获取有关该联系人的详细信息：
  
1. OSC 提供程序支持的活动的按需同步指示的可以 OSC，通过使用**getActivities**和**dynamicActivitiesLookupEx**元素。 OSC 提供程序还设置**hashFunction**元素。 所有三个元素均**功能**的子元素。 
    
2. OSC 提供程序实现的**ISocialProvider::GetCapabilities**和[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法。 
    
3. OSC 呼叫**ISocialProvider::GetCapabilities**检查**getActivities**和**dynamicActivitiesLookupEx**的值以验证 OSC 提供程序支持活动的按需的同步。 OSC 还备注 OSC 提供程序支持**hashFunction**元素的值。 
    
4. OSC 刷新，使用户可以查看选定人员的最新活动人员窗格或联系人卡片。 OSC 使用**hashFunction**元素中指定的哈希函数形成一个 XML 字符串，符合**hashedAddresses**元素的 XML 架构定义加密此人的 SMTP 地址。 
    
5. OSC 调用**ISocialSession2::GetActivitiesEx**，提供该 XML 字符串的哈希地址作为_hashedAddresses_参数，以获取_活动_参数中的用户的当前活动的集合。 _活动_参数字符串符合**activityFeed**元素的 XML 架构定义。 
    
6. 根据 XML 架构定义**activityFeed**，OSC 进一步分析要找出类型、 发布日期和有关每个活动的其他信息以及如何显示活动的_活动_字符串。 
    
7. 要获取有关选定人员的详细信息，请 OSC 调用[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)，提供的同一个 XML 字符串的哈希地址作为_personsAddresses_参数的参数。 _PersonsCollection_参数中返回有关此人的详细信息。 **FirstName**、 **lastName**和**emailAddress**，可以包括以下详细信息。 _PersonsCollection_参数符合**person**元素的 XML 架构定义。 
    
您可以找到有关本节的以下主题中的活动指定 XML 的详细信息：
  
- [概述 XML 的活动订阅源](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
- [正确显示活动的指南](guidelines-for-properly-displaying-activities.md)
    
## <a name="see-also"></a>另请参阅

- [活动源的 XML 示例](activity-feed-xml-example.md)  
- [同步朋友和活动](synchronizing-friends-and-activities.md) 
- [功能 XML](xml-for-capabilities.md)  
- [朋友 XML](xml-for-friends.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

