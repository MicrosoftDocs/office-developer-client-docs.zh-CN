---
title: activityTemplateContainer 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 74662f25-5e18-4d0b-999c-a144427ad9e3
description: ActivityTemplateContainer 元素是允许您格式活动源项目并重用指定布局 XML 模板。
ms.openlocfilehash: e744bb1bdb828003cdda7086468533b32b4bf20f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779205"
---
# <a name="activitytemplatecontainer-element"></a>activityTemplateContainer 元素

**ActivityTemplateContainer**元素是允许您格式活动源项目并重用指定布局 XML 模板。 使用 Id （**applicationID**和**templateID**），以匹配模板 (**activityTemplateContainer**) 的源的项 (**activityDetails**)。 存储布局数据作为**activityTemplate**元素的一部分。 若要引用取自单独的活动订阅源的数据，用作模板变量占位符的信息，如人员、 链接和文本。 
  
下表介绍**activityTemplateContainer**元素需要的三个元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**applicationID** <br/> |一个用于匹配具有其模板的源的项的两个唯一 Id。 如果您有多个应用程序或其他分组，这可作为第一层模板组织者。  <br/> |
|**templateID** <br/> |用于匹配具有其模板的源的项第二个唯一 ID。 这可以用作第二层模板管理器。  <br/> |
|**activityTemplate** <br/> |模板 （**图标**、**标题**和**数据**元素），以及活动 （**type**元素） 的类型的布局。  <br/> |
   
下表介绍**activityTemplate**，其中描述了布局和模板的类型的子元素。
  
|**元素**|**说明**|
|:-----|:-----|
|**icon** <br/> |链接令牌，引用该订阅源的项目的图标的 URL。  <br/> |
|**title** <br/> |订阅源所需的信息。  <br/> |
|**type** <br/> |活动，如状态、 照片或文档的更新的类型。  <br/> |
|**data** <br/> |对于订阅源的项，如图片、 文本或链接的任何其他信息。  <br/> |
   
有关示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)
  
## <a name="see-also"></a>另请参阅

- [概述 XML 的活动订阅源](overview-of-xml-for-an-activity-feed-item.md)  
- [activityDetails 元素](activitydetails-element.md)  
- [模板变量](template-variables.md)  
- [正确显示活动的指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [Outlook Social Connector 提供程序的 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

