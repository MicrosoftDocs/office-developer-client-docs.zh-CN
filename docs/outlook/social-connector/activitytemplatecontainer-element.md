---
title: activityTemplateContainer 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 74662f25-5e18-4d0b-999c-a144427ad9e3
description: activityTemplateContainer 元素是一个模板，允许你设置活动源项的格式，并重复使用指定布局的 XML。
ms.openlocfilehash: c2540b1d871e440e8f8f343a1788194c32d7dcc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413715"
---
# <a name="activitytemplatecontainer-element"></a>activityTemplateContainer 元素

**activityTemplateContainer** 元素是一个模板，允许你设置活动源项的格式，并重复使用指定布局的 XML。 使用 id (**applicationID** 和 **templateID**) 将源项目 (**activityDetails**) 与 (**activityTemplateContainer**) 。 将布局数据存储为 **activityTemplate 元素的一** 部分。 若要引用数据单个活动源项提取的内容，请使用模板变量作为人员、链接和文本等信息的占位符。 
  
下表介绍了 **activityTemplateContainer** 元素所需的三个元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**applicationID** <br/> |用于将源项与它的模板相匹配的两个唯一的标识之一。 如果你有多个应用程序或其他分组，这可用作第一层模板管理器。  <br/> |
|**templateID** <br/> |用于将源项与它的模板相匹配的第二个唯一 ID。 这可用作第二层模板管理器。  <br/> |
|**activityTemplate** <br/> |模板的布局 (**图标**、**标题** 和数据元素) ，以及活动类型 (**元素**) 。  <br/> |
   
下表介绍了 **activityTemplate** 的子元素，这些子元素描述了模板的布局和类型。
  
|**元素**|**说明**|
|:-----|:-----|
|**icon** <br/> |链接令牌，引用该源项的图标的 URL。  <br/> |
|**title** <br/> |源项的必需信息。  <br/> |
|**type** <br/> |活动类型，例如状态、照片或文档的更新。  <br/> |
|**data** <br/> |源项的其他任何信息，例如图片、文本或链接。  <br/> |
   
有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)
  
## <a name="see-also"></a>另请参阅

- [活动源项的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)  
- [activityDetails 元素](activitydetails-element.md)  
- [模板变量](template-variables.md)  
- [正确显示活动指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [OutlookSocial Connector Provider XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

