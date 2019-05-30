---
title: 活动源 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa50ca36-8d01-4770-9d9c-30a5baa146ff
description: '本主题中的 XML 示例是在为社交网络调用 ISocialSession2:: GetActivitiesEx 方法后返回到 Outlook Social Connector (.OSC) 的活动源 XML 字符串。'
ms.openlocfilehash: bb8af45f25d8ee2897a3a01e2863466aeacec4e8
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538324"
---
# <a name="activity-feed-xml-example"></a>活动源 XML 示例

本主题中的 XML 示例是在为社交网络调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法后返回到 Outlook Social CONNECTOR (.osc) 的活动源 XML 字符串。 
  
该示例显示包含以下四个活动的**Microsoft.office.server.activityfeed** XML, 每个活动都由**activityDetails**元素分隔并匹配用于显示目的的模板: 
  
- 由 Melissa Macbeth 的配置文件图片更新, 其在社交网络上的**ownerID**为4667647。 此活动指定**publisherVariable**、 **listVariable**和**pictureVariable**类型的三个模板变量 (包含在**listVariable**中)。 这些变量指定发布活动源项目的人员, 以及要更新的图片的信息 (使用**pictureVariable**的**name**、 **value**、 **altText**和**href**子元素)。
    
- 由 Michael Affronti 的配置文件图片更新, 其社会网络上的**ownerID**为5015012。 与最后一个活动类似, 此活动指定**publisherVariable**、 **listVariable**和**pictureVariable**类型的三个模板变量。 这些变量指定发布活动源项目的人员以及要更新的图片的信息。
    
- 迈克尔• Affronti 的状态更新, 显示与最后一个活动相同的 5015012 **ownerID** 。 此活动指定**publisherVariable**和**textVariable**类型的两个模板变量。 **publisherVariable**指定发布活动源项目的人员, 并**textVariable**包含状态行的**值**`is hiking on Mount Rainier this weekend!`
    
- 迈克尔• Affronti 中的博客文章, 显示与最后两个活动相同的 5015012 **ownerID** 。 此活动指定**publisherVariable**和**linkVariable**类型的两个模板变量。 **publisherVariable**指定发布活动源项目的人员, 并**linkVariable**包含详细信息 (由**linkVariable**的**name**、 **text**和**value**子元素指定)关于博客文章。
    
这四个活动中的每一个都指定一个**templateID**值, 该值与**templates**元素指定的三个模板之一相匹配。 每个模板都位于其自己的**activityTemplateContainer**元素中, 该元素由另一个**templateID**值标识, 该值也用于显示具有相同**templateID**值的活动。 
  
有关本示例中使用的 XML 元素的详细说明, 请参阅下列主题: 
  
- [活动源项目的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
## <a name="xml-example"></a>XML 示例

以下示例显示了四个活动的**Microsoft.office.server.activityfeed** XML: 两个配置文件图片更新、一个状态更新和一个博客文章。 XML 还指定三个活动显示模板, 用于显示相应的活动。 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<activityFeed xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
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

- [.OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [适用于活动的 XML](xml-for-activities.md) 
- [功能 XML 示例](capabilities-xml-example.md)  
- [友元 XML 示例](friends-xml-example.md)
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)

