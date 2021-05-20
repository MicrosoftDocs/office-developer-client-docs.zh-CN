---
title: 活动源 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa50ca36-8d01-4770-9d9c-30a5baa146ff
description: 本主题中的 XML 示例是在调用社交网络的 ISocialSession2：：GetActivitiesEx 方法后返回到 Outlook Social Connector (OSC) 的活动源 XML 字符串。
ms.openlocfilehash: bb8af45f25d8ee2897a3a01e2863466aeacec4e8
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538324"
---
# <a name="activity-feed-xml-example"></a>活动源 XML 示例

本主题中的 XML 示例是在调用社交网络的[ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md)方法后返回到 Outlook Social Connector (OSC) 的活动源 XML 字符串。 
  
该示例演示包含以下四个活动的 **activityFeed** XML，每个活动由 **activityDetails** 元素分隔，并出于显示目的匹配模板： 
  
- Melissa Macbeth 提供的个人资料图片更新，其社交网络上的 **ownerID** 为 4667647。 此活动指定类型 **为 publisherVariable、listVariable** 和 **pictureVariable** (的三个模板变量，这些变量包含在 **listVariable**) 。 这些变量指定发布活动源项目的人，以及使用 **pictureVariable** 属性的名称、**值****、altText** 和 **href** 子元素更新 (的图片) 。
    
- Michael Affronti 在社交网络上的 **ownerID** 为 5015012 的配置文件图片更新。 与上一个活动类似，此活动指定 **publisherVariable、listVariable** 和 **pictureVariable** 类型的三个模板变量。 这些变量指定发布活动源项的人以及要更新的图片的信息。
    
- Michael Affronti 的状态更新，显示与上次活动相同的 **ownerID** 5015012。 此活动指定 publisherVariable 和 **textVariable** 类型的两 **个模板变量**。 **publisherVariable** 指定发布活动源项目的人 **，textVariable** 包括状态行的值`is hiking on Mount Rainier this weekend!`
    
- Michael Affronti 的一篇博客文章，其中显示与最后两个活动相同的 **ownerID** 5015012。 此活动指定 **publisherVariable** 和 **linkVariable** 类型的两个模板变量。 **publisherVariable** 指定发布活动源项目的人 **，linkVariable** 包括由 **linkVariable**) 的名称、**文本** 和 **值** 子元素指定的有关该博客文章的详细信息 () 。
    
这四个活动都指定了一个 **templateID** 值，该值与 **templates** 元素指定的三个模板之一匹配。 每个模板位于其自己的 **activityTemplateContainer** 元素中，由 **templateID** 值标识，该元素还用于显示具有相同 **templateID** 值的活动。 
  
有关示例中使用的 XML 元素的详细说明，请参阅下列主题： 
  
- [活动源项的 XML 概述](overview-of-xml-for-an-activity-feed-item.md)
    
- [activityDetails 元素](activitydetails-element.md)
    
- [activityTemplateContainer 元素](activitytemplatecontainer-element.md)
    
- [模板变量](template-variables.md)
    
## <a name="xml-example"></a>XML 示例

以下示例显示包含四个 **活动的 activityFeed** XML：两个配置文件图片更新、一个状态更新和一个博客文章。 XML 还指定用于显示相应活动的三个活动显示模板。 
  
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

- [OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [活动的 XML](xml-for-activities.md) 
- [Capabilities XML 示例](capabilities-xml-example.md)  
- [好友 XML 示例](friends-xml-example.md)
- [OutlookSocial Connector Provider XML 架构](outlook-social-connector-provider-xml-schema.md)

