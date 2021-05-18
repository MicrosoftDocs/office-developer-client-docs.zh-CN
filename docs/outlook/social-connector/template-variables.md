---
title: 模板变量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6f8f6af2-c7fa-4135-9532-7af5fc643b0d
description: 由 templateVariable (表示的模板变量) 指定活动模板中活动源项的数据。
ms.openlocfilehash: 9b37665488f0f1e2bd205fb7d4a5d2201697d7c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404370"
---
# <a name="template-variables"></a>模板变量

由 **templateVariable** (表示的模板变量) 指定活动模板中的活动源项的数据。 
  
有关活动源 XML 的示例，请参阅 [活动源 XML 示例](activity-feed-xml-example.md)。

下表显示了受支持的模板变量的类型，每种变量都由相应的 XML 枚举值表示。
  
|**模板变量的类型**|**说明**|
|:-----|:-----|
|**entityVariable** <br/> |人员、组或事物。  <br/> |
|**linkVariable** <br/> |链接。  <br/> |
|**listVariable** <br/> |一组对象。  <br/> |
|**pictureVariable** <br/> |图片。  <br/> |
|**publisherVariable** <br/> |活动源项的发布者。  <br/> |
|**textVariable** <br/> |一个文本块。  <br/> |
   
每种类型的模板变量都有必需元素来指定有关该变量的数据。 模板变量的指定方式如下：
  
`<templateVariable type="variable type">`
  
## <a name="list-template-variable"></a>列表模板变量

可以指定包含在列表内且由 **listVariable** 和 **listItems** (分隔的模板变量) 如下所示： 
  
`<simpleTemplateVariable type="variable type of text, link, or picture">`
  
**listVariable** 类型的模板变量是对象的容器。 它可以包含链接Variable 或 **textVariable** 类型的 (或 **pictureVariable** 类型的) 或图片 (逗号分隔) 。 列表可以包含最多五个链接项、五个文本项或五个图片。 
  
OUTLOOK Social Connector (OSC) Windows 系统区域设置本地化链接或文本列表项。
  
若要在活动源项中正确分析和显示图片，必须在列表中包括图片。 所有图片的大小都调整为 52 像素高。 不调整图片的宽度。
  
## <a name="template-variable-elements"></a>模板变量元素

本节介绍每种模板变量类型支持的必需元素和可选元素。
  
### <a name="entityvariable"></a>entityVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**id** <br/> |用户的唯一 ID。 必填。  <br/> |
|**nameHint** <br/> |要显示在源项中的名称。 可选。  <br/> |
|**profileUrl** <br/> |人员个人资料的 URL，如果人员姓名存在，则用作源项中人员姓名的超链接。 可选。  <br/> |
|**emailAddress** <br/> |用于在 Outlook 中更新此人的联系信息的电子邮件地址。 可选。  <br/> |
   
### <a name="linkvariable"></a>linkVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**value** <br/> |此链接的 URL。 必填。  <br/> |
|**text** <br/> |要显示的链接文本，而不是 URL 本身。 可选。  <br/> |
   
### <a name="listvariable"></a>listVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**listItems** <br/> |列表中项的容器。 必填。  <br/> |
   
### <a name="picturevariable"></a>pictureVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**value** <br/> |图片的 URL。 必填。  <br/> |
|**altText** <br/> |为辅助功能和用户将鼠标指针移动到图片上时显示的备用文本。 可选。  <br/> |
|**href** <br/> |当用户单击图片时使用的超链接（如果所需目标不是 value 元素指定的 **图片 URL）。** 可选。  <br/> |
   
### <a name="publishervariable"></a>publisherVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**id** <br/> |用户的唯一 ID。 必填。  <br/> |
|**nameHint** <br/> |要显示在源项中的名称。 可选。  <br/> |
|**profileUrl** <br/> |人员个人资料的 URL，如果人员姓名存在，则用作源项中人员姓名的超链接。 可选。  <br/> |
|**emailAddress** <br/> |用于在 Outlook 中更新此人的联系信息的电子邮件地址。 可选。  <br/> |
   
### <a name="textvariable"></a>textVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必填。  <br/> |
|**value** <br/> |要显示的文本。 可选。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [活动源项的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)  
- [activityDetails 元素](activitydetails-element.md)  
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)  
- [正确显示活动指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

