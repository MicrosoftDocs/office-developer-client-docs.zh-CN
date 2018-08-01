---
title: 模板变量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6f8f6af2-c7fa-4135-9532-7af5fc643b0d
description: 模板变量 （由 templateVariable 元素） 的实例指定活动源中活动模板的项目的数据。
ms.openlocfilehash: 99f4c2de586447fb0361e528bcd33d62b79e0fb1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779352"
---
# <a name="template-variables"></a>模板变量

模板变量 （由**templateVariable**元素） 的实例指定活动源中活动模板的项目的数据。 
  
示例活动的源 XML，请参阅[活动源 XML 示例](activity-feed-xml-example.md)。

下表显示了每个相应的 XML 枚举值由表示支持的模板变量的类型。
  
|**模板变量的类型**|**说明**|
|:-----|:-----|
|**entityVariable** <br/> |人员、 组或事物。  <br/> |
|**linkVariable** <br/> |链接。  <br/> |
|**listVariable** <br/> |一组对象。  <br/> |
|**pictureVariable** <br/> |图片。  <br/> |
|**publisherVariable** <br/> |发布者的活动订阅源。  <br/> |
|**textVariable** <br/> |文本块。  <br/> |
   
每种类型的模板变量需要元素指定有关该变量的数据。 模板变量，如下所示指定：
  
`<templateVariable type="variable type">`
  
## <a name="list-template-variable"></a>列表模板变量

您可以指定模板变量包含在列表 （分隔的**listVariable**和**listItems**元素），如下所示： 
  
`<simpleTemplateVariable type="variable type of text, link, or picture">`
  
**ListVariable**类型的模板变量是对象的容器。 它可以包含 （ **linkVariable**或**textVariable**类型） 的逗号分隔的项目或 （ **pictureVariable**类型） 的图片。 列表可以包含最多五个链接项目、 五个文本项目或五个图片。 
  
Outlook Social Connector (OSC) 本地化链接或文本根据 Windows 系统区域设置的列表项。
  
要正确分析，并在活动源项目中显示图片，您必须包括列表中的图片。 所有图片调整都大小为 52 像素高。 图片的宽度不调整大小。
  
## <a name="template-variable-elements"></a>模板变量元素

本节介绍支持的每种类型的模板变量的必需的和可选元素。
  
### <a name="entityvariable"></a>entityVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**id** <br/> |用户的唯一 ID。 必需。  <br/> |
|**nameHint** <br/> |要馈送项目中显示的名称。 可选。  <br/> |
|**profileUrl** <br/> |将用于为超链接中的订阅源的项目，此人的姓名如果存在此人的姓名的人的配置文件的 URL。 可选。  <br/> |
|**emailAddress** <br/> |用于更新此人的联系人信息在 Outlook 中的电子邮件地址。 可选。  <br/> |
   
### <a name="linkvariable"></a>linkVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**value** <br/> |此链接的 URL。 必需。  <br/> |
|**text** <br/> |要显示而不是该 URL 本身的链接文本。 可选。  <br/> |
   
### <a name="listvariable"></a>listVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**列表项目** <br/> |在列表中的项的容器。 必需。  <br/> |
   
### <a name="picturevariable"></a>pictureVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**value** <br/> |图片 URL。 必需。  <br/> |
|**altText** <br/> |备用辅助功能和用户将鼠标指针移到图片上时显示的文本。 可选。  <br/> |
|**href** <br/> |若要使用当用户单击该图片，如果所需的目标不是**值**元素所指定的图片 URL 超链接。 可选。  <br/> |
   
### <a name="publishervariable"></a>publisherVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**id** <br/> |用户的唯一 ID。 必需。  <br/> |
|**nameHint** <br/> |要馈送项目中显示的名称。 可选。  <br/> |
|**profileUrl** <br/> |将用于为超链接中的订阅源的项目，此人的姓名如果存在此人的姓名的人的配置文件的 URL。 可选。  <br/> |
|**emailAddress** <br/> |用于更新此人的联系人信息在 Outlook 中的电子邮件地址。 可选。  <br/> |
   
### <a name="textvariable"></a>textVariable

|**元素**|**说明**|
|:-----|:-----|
|**name** <br/> |变量的名称。 必需。  <br/> |
|**value** <br/> |要显示的文本。 可选。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [概述 XML 的活动订阅源](overview-of-xml-for-an-activity-feed-item.md)  
- [activityDetails 元素](activitydetails-element.md)  
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)  
- [正确显示活动的指南](guidelines-for-properly-displaying-activities.md)  
- [活动的 XML](xml-for-activities.md)  
- [Outlook Social Connector 提供程序的 XML 架构](outlook-social-connector-provider-xml-schema.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

