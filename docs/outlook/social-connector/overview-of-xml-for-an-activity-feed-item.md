---
title: 活动源项的 XML 概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 366550fa-e787-4ca0-bfe1-a7890dfc27c6
description: 活动源由社交网络上发生的一个或多个活动组成。 每个活动源由一个 activityFeed 元素表示，其特征为以下三条信息：
ms.openlocfilehash: 971c54cf69a65bebbe4fd04e8608e88b89145bb4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439945"
---
# <a name="overview-of-xml-for-an-activity-feed-item"></a>活动源项的 XML 概述

活动源由社交网络上发生的一个或多个活动组成。 每个活动源由一个 **activityFeed** 元素表示，其特征为以下三条信息： 
  
- **network**— 源自活动的社交网络的名称。
    
- **activities**— 该社交网络上登录的用户帐户上发生的活动的容器。
    
- **templates**— 用于显示活动中的相应活动项的模板 **容器**。
    
若要创建活动源项，您必须遵循 OSC Outlook扩展性 XML 架构 () Social Connector。 图 1 显示了活动源 XML 结构。
  
**图 1.活动源 XML 结构**

![活动 XML 结构](media/odc_ol14_ta_OSC_Fig06.gif)
  
对于每个活动源项，此架构的两个最重要的部分为 **activityDetails** 和 **activityTemplateContainer** 元素： 
  
- **activityDetails** 元素存储每个活动源项的特定信息，如活动所有者的名称或上载图片的 URL。 
    
- **activityTemplateContainer** 元素存储每个活动源项的格式或布局。 它包含由单个 **activityTemplate** 元素表示的模板，这些模板可重复使用用于多个源项。 
    
对于单个活动源项 **，activityTemplate** 元素指定以下四条信息： 
  
- **icon**— 指定用于显示活动源项目的图标的 URL。
    
- **title**— 描述活动源项。
    
- **type**— 指定活动类型，例如状态、照片或文档更新。
    
- **data**— 指定与活动源项目一起显示的任何额外信息。
    
> [!TIP]
> 活动源中显示的图标始终与 **ISocialProvider：：SocialNetworkIcon** 属性返回的提供程序图标相同。 
  
有关 **activityDetails** 元素 **、activityTemplateContainer** 元素、模板标记和模板变量详细信息，请参阅以下主题： 
  
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
- [正确显示活动指南](guidelines-for-properly-displaying-activities.md)
    
有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)。
  
## <a name="see-also"></a>另请参阅

- [活动的 XML](xml-for-activities.md) 
- [OutlookSocial Connector Provider XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

