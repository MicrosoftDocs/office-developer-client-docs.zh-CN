---
title: 活动源项的 XML 概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 366550fa-e787-4ca0-bfe1-a7890dfc27c6
description: '活动源由社交网络中发生的一个或多个活动组成。 每个活动源均由一个 microsoft.office.server.activityfeed 元素表示, 并由以下三条信息组成:'
ms.openlocfilehash: 971c54cf69a65bebbe4fd04e8608e88b89145bb4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329288"
---
# <a name="overview-of-xml-for-an-activity-feed-item"></a>活动源项的 XML 概述

活动源由社交网络中发生的一个或多个活动组成。 每个活动源均由一个**microsoft.office.server.activityfeed**元素表示, 并由以下三条信息组成: 
  
- **网络**—活动源自的社交网络的名称。
    
- **活动**—在该社交网络上登录用户帐户上发生的活动的容器。
    
- **模板**-用于在**活动**中显示相应活动项的模板的容器。
    
若要创建活动源项目, 您必须符合 Outlook Social Connector (.osc) 提供程序扩展性 XML 架构。 图1显示了活动源 XML 结构。
  
**图1。活动源 XML 结构**

![活动 XML 结构](media/odc_ol14_ta_OSC_Fig06.gif)
  
对于每个活动源项目, 此架构的两个最重要部分是**activityDetails**和**activityTemplateContainer**元素: 
  
- **activityDetails**元素存储每个活动源项的特定信息, 例如活动所有者的名称或上载的图片的 URL。 
    
- **activityTemplateContainer**元素存储每个活动源项目的格式或布局。 它由各个**activityTemplate**元素表示的模板组成, 这些模板可重复用于多个订阅源项。 
    
对于单个活动源项, **activityTemplate**元素将指定以下四条信息: 
  
- **图标**—指定用于显示活动源项目的图标的 URL。
    
- **标题**—描述活动源项目。
    
- **类型**—指定活动的类型, 如状态、照片或文档更新。
    
- **data**-指定与活动源项目一起显示的任何额外信息。
    
> [!TIP]
> 活动源中显示的图标总是与**ISocialProvider:: SocialNetworkIcon**属性返回的提供程序图标相同。 
  
有关**activityDetails**元素、 **activityTemplateContainer**元素、模板标记和模板变量的详细信息, 请参阅以下主题: 
  
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
- [正确显示活动的准则](guidelines-for-properly-displaying-activities.md)
    
有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)。
  
## <a name="see-also"></a>另请参阅

- [适用于活动的 XML](xml-for-activities.md) 
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

