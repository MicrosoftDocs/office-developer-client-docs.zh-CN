---
title: activityDetails 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c103d48d-53ca-4b19-b16f-2862379587ef
description: activityDetails 元素存储单个活动源项目的原始数据。 每个活动源项都必须具有其自己的 activityDetails 元素。 activityDetails 元素中的数据使用 name 元素在活动模板中引用。
ms.openlocfilehash: fd9c2136e8e2b687fa281ecda71039809848f63c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281347"
---
# <a name="activitydetails-element"></a>activityDetails 元素

**activityDetails**元素存储单个活动源项目的原始数据。 每个活动源项都必须具有其自己的**activityDetails**元素。 **activityDetails**元素中的数据使用**name**元素在活动模板中引用。 **activityDetails**元素中的每条数据都必须具有**name**元素。 
  
下表描述了**activityDetails**元素所需的六个元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**ownerID** <br/> |生成此活动源项目的社交网络上的用户的 ID。  <br/> |
|**objectID** <br/> |用于检测重复的订阅源项目的活动源项目的唯一字符串。  <br/> |
|**applicationId** <br/> |用于将活动源项目与模板相匹配的两个唯一 id 之一。 如果您有多个应用程序或其他分组, 则可用作第一层模板组织者。  <br/> |
|**templateId** <br/> |用于将活动源项目与其模板匹配的第二个唯一 ID。 这可用作第二层模板组织者。  <br/> |
|**publishDate** <br/> |活动源项目的发布日期和时间。  <br/> |
|**templateVariables** <br/> |要在活动源项模板的令牌中使用的数据。  <br/> |
   
有关活动源 xml 的示例, 请参阅[活动源 xml 示例](activity-feed-xml-example.md)
  
## <a name="see-also"></a>另请参阅

- [活动源项目的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)  
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)  
- [模板变量](template-variables.md) 
- [正确显示活动的准则](guidelines-for-properly-displaying-activities.md)  
- [适用于活动的 XML](xml-for-activities.md)  
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

