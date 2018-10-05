---
title: 活动源的 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa50ca36-8d01-4770-9d9c-30a5baa146ff
description: 本主题中的 XML 示例为活动源后它为社交网络调用 ISocialSession2::GetActivitiesEx 方法返回 Outlook Social Connector (OSC) 到的 XML 字符串。
ms.openlocfilehash: 6370b559c5160bfa48d32afa77715e9a7c126aab
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390462"
---
# <a name="activity-feed-xml-example"></a>活动源的 XML 示例

本主题中的 XML 示例为活动源后它为社交网络调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法返回 Outlook Social Connector (OSC) 到的 XML 字符串。 
  
该示例演示**activityFeed**包含以下四个活动的 XML，每个分隔**activityDetails**元素和匹配的模板显示目的： 
  
- 通过 Melissa Macbeth，其**ownerID**社交网络上是 4667647 更新配置文件图片。 此活动指定三个模板变量类型**publisherVariable**、 **listVariable**，和**pictureVariable** （这在**listVariable**括起来）。 这些变量指定发布活动源项目，并图片 （通过使用**pictureVariable**的**名称**、**值**、 **altText**和**href**子元素） 更新的信息的人员。
    
- 通过在社交网络其**ownerID**是 5015012 Michael Affronti 更新配置文件图片。 最后一次活动类似，此活动指定类型**publisherVariable**、 **listVariable**和**pictureVariable**的三个模板变量。 这些变量指定发布活动源项目和图片要更新的信息的人员。
    
- 通过 Michael Affronti，显示同一**ownerID** 5015012 的最后一次活动为状态更新。 此活动指定两个模板的变量类型**publisherVariable**和**textVariable**。 **publisherVariable**指定用户发布的活动源项目，并**textVariable**包括状态行**值**`is hiking on Mount Rainier this weekend!`
    
- Michael Affronti，显示同一**ownerID**的 5015012 作为最后两个活动的博客文章。 此活动指定两个模板的变量类型**publisherVariable**和**linkVariable**。 **publisherVariable**指定用户发布的活动订阅源，并**linkVariable**进一步包括 （由**linkVariable**的**名称**、**文本**和**值**子元素指定） 的信息有关的博客文章。
    
指定一个**templateID**值，该值匹配**模板**元素所指定的三个模板的一个每四个活动。 每个模板都由一个**templateID**值，也可用于显示活动具有相同的**templateID**值标识自己**activityTemplateContainer**元素中。 
  
在示例中使用的 XML 元素的详细说明，请参阅下列主题： 
  
- [概述 XML 的活动订阅源](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
## <a name="xml-example"></a>XML 示例

下面的示例演示**activityFeed**四项活动的 XML： 两个配置文件图片更新、 状态更新和博客文章。 XML 还会指定用于显示相应的活动的三个活动显示模板。 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<activityFeed xmlns="https://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
  <network>Contoso</network>
  <activities>
    <activityDetails>
      <ownerID>4667647</ownerID>
      <objectID>9d2b5e6360894a21d56d7d0b5969d23cf4034a31</objectID>
      <applicationID>2</applicationID>
      <templateID>1</templateID>
      <publishDate>2010-03-05T17:19:57</publishDate>
      <templateVariables>
        <templateVariable type="publisherVariable">
          <name>Publisher</name>
          <id>4667647</id>
          <nameHint>Melissa Macbeth</nameHint>
          <profileUrl>https://www.contoso.com/</profileUrl>
        </templateVariable>
        <templateVariable type="listVariable">
          <name>ProfilePhoto</name>
          <listItems>
            <simpleTemplateVariable type="pictureVariable">
              <name>Photo</name>
              <value>https://office.microsoft.com/global/images/default.aspx?assetid=ZA103873861033</value>
              <altText>Melissa Macbeth</altText>
              <href>https://office.microsoft.com/global/images/default.aspx?assetid=ZA103873861033</href>
            </simpleTemplateVariable>
          </listItems>
        </templateVariable>
      </templateVariables>
    </activityDetails>
    <activityDetails>
      <ownerID>5015012</ownerID>
      <objectID>9d2b5e6360894a21d56d7d0b5969d23cf4034a32</objectID>
      <applicationID>2</applicationID>
      <templateID>1</templateID>
      <publishDate>2010-03-08T17:19:57</publishDate>
      <templateVariables>
        <templateVariable type="publisherVariable">
          <name>Publisher</name>
          <id>5015012</id>
          <nameHint>Michael Affronti</nameHint>
          <profileUrl>https://www.contoso.com/</profileUrl>
        </templateVariable>
        <templateVariable type="listVariable">
          <name>ProfilePhoto</name>
          <listItems>
            <simpleTemplateVariable type="pictureVariable">
              <name>Photo</name>
              <value>https://office.microsoft.com/global/images/default.aspx?assetid=ZA103895491033</value>
              <altText>Michael Affronti</altText>
              <href>https://office.microsoft.com/global/images/default.aspx?assetid=ZA103895491033</href>
            </simpleTemplateVariable>
          </listItems>
        </templateVariable>
      </templateVariables>
    </activityDetails>
    <activityDetails>
      <ownerID>5015012</ownerID>
      <objectID>9d2b5e6360894a21d56d7d0b5969d23cf4034a38</objectID>
      <applicationID>2</applicationID>
      <templateID>2</templateID>
      <publishDate>2010-03-08T18:30:00</publishDate>
      <templateVariables>
        <templateVariable type="publisherVariable">
          <name>Publisher</name>
          <id>5015012</id>
          <nameHint>Michael Affronti</nameHint>
          <profileUrl>https://www.contoso.com</profileUrl>
        </templateVariable>
        <templateVariable type="textVariable">
          <name>statusText</name>
          <value>is hiking on Mount Rainier this weekend!</value>
        </templateVariable>
      </templateVariables>
    </activityDetails>
    <activityDetails>
      <ownerID>5015012</ownerID>
      <objectID>9d2b5e6360894a21d56d7d0b5969d23cf4034a39</objectID>
      <applicationID>2</applicationID>
      <templateID>3</templateID>
      <publishDate>2010-03-04T15:00:00</publishDate>
      <templateVariables>
        <templateVariable type="publisherVariable">
          <name>Publisher</name>
          <id>5015012</id>
          <nameHint>Michael Affronti</nameHint>
          <profileUrl>https://www.contoso.com/</profileUrl>
        </templateVariable>
        <templateVariable type="linkVariable">
          <name>blogPost</name>
          <text>Connect your Inbox to Facebook and Windows Live with the Outlook Social Connector</text>
          <value>https://blogs.office.com/b/office_blog/archive/2010/07/13/connect-to-facebook-and-windows-live-with-the-outlook-social-connector.aspx</value>
        </templateVariable>
      </templateVariables>
    </activityDetails>
  </activities>
  <templates>
    <activityTemplateContainer>
      <applicationID>2</applicationID>
      <templateID>1</templateID>
      <activityTemplate>
        <type>Photo</type>
        <title>{publisher:Publisher} has a new profile photo: </title>
        <data>{list:ProfilePhoto({picture:Photo})}</data>
        <icon>https://www.microsoft.com/about/images/rss_button.gif</icon>
      </activityTemplate>
    </activityTemplateContainer>
    <activityTemplateContainer>
      <applicationID>2</applicationID>
      <templateID>2</templateID>
      <activityTemplate>
        <type>Status Update</type>
        <title>{publisher:Publisher}: {text:statusText}</title>
                <data></data>
        <icon>https://www.microsoft.com/about/images/rss_button.gif</icon>
      </activityTemplate>
    </activityTemplateContainer>
    <activityTemplateContainer>
      <applicationID>2</applicationID>
      <templateID>3</templateID>
      <activityTemplate>
        <type>Other</type>
        <title>{publisher:Publisher} wrote a new blog post {link:blogPost}</title>
                <data></data>
        <icon>https://www.microsoft.com/about/images/rss_button.gif</icon>
      </activityTemplate>
    </activityTemplateContainer>
  </templates>
</activityFeed>

```

## <a name="see-also"></a>另请参阅

- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [活动的 XML](xml-for-activities.md) 
- [功能 XML 示例](capabilities-xml-example.md)  
- [朋友 XML 示例](friends-xml-example.md)
- [Outlook Social Connector 提供程序的 XML 架构](outlook-social-connector-provider-xml-schema.md)

