---
title: 活动的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: acc4a555-a3bf-4a79-86dc-aba6477733b8
description: 本主题包含一个示例方案，其中显示了 OSC 提供程序实现和 OSC 为获取活动信息而调用的 Outlook Social Connector (OSC) 提供程序扩展性 API。 信息以符合 OSC 提供程序 XML 架构的 XML 字符串表示。
ms.openlocfilehash: a4f1c6ce1f33b59811f6a6fecb737cd1f737946b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409627"
---
# <a name="xml-for-activities"></a>活动的 XML

本主题包含一个示例方案，其中显示了 OSC 提供程序实现和 OSC 为获取活动信息而调用的 Outlook Social Connector (OSC) 提供程序扩展性 API。 信息以符合 OSC 提供程序 XML 架构的 XML 字符串表示。
  
OSC 提供程序 XML 架构允许 OSC 提供程序定义活动。 活动信息可能包括源自活动源项目的社交网络、每个活动源项目的详细信息 (如活动) 的所有者、类型和发布日期，以及用于显示活动的模板。 为了支持在人员窗格或联系人卡片上显示活动，社交网络的 OSC 提供程序必须实现并返回正确的活动 XML。 有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)。 有关同步好友活动的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。 有关 OSC 提供程序 XML 架构的完整定义，包括哪些元素是必需的或可选的，请参阅Outlook[连接器提供程序 XML 架构。](outlook-social-connector-provider-xml-schema.md) 
  
在下列方案中，OSC 动态同步在人员窗格中选择的人的活动，并获取此人的详细信息：
  
1. 支持按需同步活动的 OSC 提供程序使用 **getActivities** 和 **dynamicActivitiesLookupEx** 元素将指示到 OSC。 OSC 提供程序还会设置 **hashFunction** 元素。 所有三个元素都是功能的 **子元素**。 
    
2. OSC 提供程序实现 **ISocialProvider：：GetCapabilities** 和 [ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md) 方法。 
    
3. OSC 调用 **ISocialProvider：：GetCapabilities** 以检查 **getActivities** 和 **dynamicActivitiesLookupEx** 的值，以验证 OSC 提供程序是否支持按需同步活动。 OSC 还记下 OSC 提供程序支持的 **hashFunction** 元素的值。 
    
4. OSC 刷新人员窗格或联系人卡片，让用户看到所选人员的最新活动。 OSC 使用 **hashFunction** 元素中指定的哈希函数对个人的 SMTP 地址进行加密，形成一个符合 **hashedAddresses** 元素的 XML 架构定义的 XML 字符串。 
    
5. OSC 调用 **ISocialSession2：：GetActivitiesEx，** 将哈希地址的此 XML 字符串作为  _hashedAddresses_ 参数提供，以在  _activities_ 参数中获取此人的当前活动集合。 _activities_ 参数字符串符合 **activityFeed** 元素的 XML 架构定义。 
    
6. 基于 **activityFeed** 的 XML 架构定义，OSC 进一步分析活动字符串，以查找有关每个活动的类型、发布日期和其他信息，以及如何显示活动。 
    
7. 为了获取选定人员的详细信息，OSC 调用 [ISocialSession2：：GetPeopleDetails，](isocialsession2-getpeopledetails.md)提供与  _personAddresses_ 参数参数相同的哈希地址 XML 字符串。 有关人员的详细信息在  _personCollection 参数_ 中返回。 这些详细信息可能包括 **firstName** **、lastName** 和 **emailAddress**。 _personCollection_ 参数符合 **person** 元素的 XML 架构定义。 
    
有关为活动指定 XML 的信息，请参阅本节的以下主题：
  
- [活动源项的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
- [正确显示活动指南](guidelines-for-properly-displaying-activities.md)
    
## <a name="see-also"></a>另请参阅

- [活动源 XML 示例](activity-feed-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md) 
- [功能的 XML](xml-for-capabilities.md)  
- [好友 XML](xml-for-friends.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

