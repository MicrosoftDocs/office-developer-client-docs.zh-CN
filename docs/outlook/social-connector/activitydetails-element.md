---
title: activityDetails 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c103d48d-53ca-4b19-b16f-2862379587ef
description: activityDetails 元素存储单个活动源项的原始数据。 每个活动源项都必须有自己的 activityDetails 元素。 activityDetails 元素中的数据通过使用 name 元素在活动模板中引用。
ms.openlocfilehash: fd9c2136e8e2b687fa281ecda71039809848f63c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434870"
---
# <a name="activitydetails-element"></a>activityDetails 元素

**activityDetails** 元素存储单个活动源项的原始数据。 每个活动源项都必须有自己的 **activityDetails** 元素。 **activityDetails** 元素中的数据通过使用 name 元素在活动 **模板中** 引用。 **activityDetails 元素** 中每段数据都必须有 **一个 name** 元素。 
  
下表介绍了 **activityDetails 元素** 所需的六个元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**ownerID** <br/> |社交网络上生成此活动源项的用户的 ID。  <br/> |
|**objectID** <br/> |活动源项的唯一字符串，用于检测重复的源项。  <br/> |
|**applicationId** <br/> |用于将活动源项与活动源项及其模板相匹配的两个唯一的标识之一。 如果你有多个应用程序或其他分组，这可用作第一层模板管理器。  <br/> |
|**templateId** <br/> |用于将活动源项与活动源项及其模板相匹配的第二个唯一 ID。 这可用作第二层模板管理器。  <br/> |
|**publishDate** <br/> |活动源项目的发布日期和时间。  <br/> |
|**templateVariables** <br/> |在活动源项模板的令牌中使用的数据。  <br/> |
   
有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)
  
## <a name="see-also"></a>另请参阅

- [活动源项的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)  
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)  
- [模板变量](template-variables.md) 
- [正确显示活动指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [OutlookSocial Connector Provider XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

