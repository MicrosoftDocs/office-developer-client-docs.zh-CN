---
title: activityDetails 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c103d48d-53ca-4b19-b16f-2862379587ef
description: ActivityDetails 元素存储单个活动源项目的原始数据。 每个活动源项必须具有自己 activityDetails 元素。 使用名称元素中活动模板引用了 activityDetails 元素中的数据。
ms.openlocfilehash: c326017a038dff138d690b020a98972a08212690
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779202"
---
# <a name="activitydetails-element"></a>activityDetails 元素

**ActivityDetails**元素存储单个活动源项目的原始数据。 每个活动源项必须具有自己**activityDetails**元素。 使用**名称**元素中活动模板引用了**activityDetails**元素中的数据。 每条**activityDetails**元素中的数据必须具有**name**元素。 
  
下表介绍**activityDetails**元素需要的六个元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**ownerID** <br/> |社交网络产生此活动用户的 ID 的订阅源。  <br/> |
|**objectID** <br/> |活动的唯一字符串源来检测重复源项目的项目。  <br/> |
|**applicationId** <br/> |一个用于匹配活动的两个唯一 Id 源具有其模板的项目。 如果您有多个应用程序或其他分组，这可作为第一层模板组织者。  <br/> |
|**templateId** <br/> |用于匹配活动的第二个唯一 ID 源具有其模板的项目。 这可以用作第二层模板管理器。  <br/> |
|**publishDate** <br/> |已发布的日期和时间的活动订阅源。  <br/> |
|**templateVariables** <br/> |要用于活动的令牌中的数据源项目模板。  <br/> |
   
有关示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)
  
## <a name="see-also"></a>另请参阅

- [概述 XML 的活动订阅源](overview-of-xml-for-an-activity-feed-item.md)  
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)  
- [模板变量](template-variables.md) 
- [正确显示活动的指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [Outlook Social Connector 提供程序的 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

