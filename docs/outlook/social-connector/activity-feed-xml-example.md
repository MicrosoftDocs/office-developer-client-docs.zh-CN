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
# <a name="activity-feed-xml-example"></a><span data-ttu-id="e90a3-103">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e90a3-103">Activity Feed XML Example</span></span>

<span data-ttu-id="e90a3-104">本主题中的 XML 示例是在调用社交网络的[ISocialSession2：：GetActivitiesEx](isocialsession2-getactivitiesex.md)方法后返回到 Outlook Social Connector (OSC) 的活动源 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="e90a3-104">The XML example in this topic is an activity feed XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method for a social network.</span></span> 
  
<span data-ttu-id="e90a3-105">该示例演示包含以下四个活动的 **activityFeed** XML，每个活动由 **activityDetails** 元素分隔，并出于显示目的匹配模板：</span><span class="sxs-lookup"><span data-stu-id="e90a3-105">The example shows the **activityFeed** XML that contains the following four activities, each delimited by the **activityDetails** element and matching a template for display purposes:</span></span> 
  
- <span data-ttu-id="e90a3-106">Melissa Macbeth 提供的个人资料图片更新，其社交网络上的 **ownerID** 为 4667647。</span><span class="sxs-lookup"><span data-stu-id="e90a3-106">A profile picture update by Melissa Macbeth, whose **ownerID** on the social network is 4667647.</span></span> <span data-ttu-id="e90a3-107">此活动指定类型 **为 publisherVariable、listVariable** 和 **pictureVariable** (的三个模板变量，这些变量包含在 **listVariable**) 。</span><span class="sxs-lookup"><span data-stu-id="e90a3-107">This activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable** (which is enclosed in **listVariable**).</span></span> <span data-ttu-id="e90a3-108">这些变量指定发布活动源项目的人，以及使用 **pictureVariable** 属性的名称、**值\*\*\*\*、altText** 和 **href** 子元素更新 (的图片) 。</span><span class="sxs-lookup"><span data-stu-id="e90a3-108">These variables specify the person who published the activity feed item, and information for the picture to be updated (by using the **name**, **value**, **altText**, and **href** child elements of **pictureVariable**).</span></span>
    
- <span data-ttu-id="e90a3-109">Michael Affronti 在社交网络上的 **ownerID** 为 5015012 的配置文件图片更新。</span><span class="sxs-lookup"><span data-stu-id="e90a3-109">A profile picture update by Michael Affronti whose **ownerID** on the social network is 5015012.</span></span> <span data-ttu-id="e90a3-110">与上一个活动类似，此活动指定 **publisherVariable、listVariable** 和 **pictureVariable** 类型的三个模板变量。</span><span class="sxs-lookup"><span data-stu-id="e90a3-110">Similar to the last activity, this activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable**.</span></span> <span data-ttu-id="e90a3-111">这些变量指定发布活动源项的人以及要更新的图片的信息。</span><span class="sxs-lookup"><span data-stu-id="e90a3-111">These variables specify the person who published the activity feed item and information for the picture to be updated.</span></span>
    
- <span data-ttu-id="e90a3-112">Michael Affronti 的状态更新，显示与上次活动相同的 **ownerID** 5015012。</span><span class="sxs-lookup"><span data-stu-id="e90a3-112">A status update by Michael Affronti, showing the same **ownerID** of 5015012 as the last activity.</span></span> <span data-ttu-id="e90a3-113">此活动指定 publisherVariable 和 **textVariable** 类型的两 **个模板变量**。</span><span class="sxs-lookup"><span data-stu-id="e90a3-113">This activity specifies two template variables of type **publisherVariable** and **textVariable**.</span></span> <span data-ttu-id="e90a3-114">**publisherVariable** 指定发布活动源项目的人 **，textVariable** 包括状态行的值`is hiking on Mount Rainier this weekend!`</span><span class="sxs-lookup"><span data-stu-id="e90a3-114">**publisherVariable** specifies the person who published the activity feed item, and **textVariable** includes a **value** of the status line  `is hiking on Mount Rainier this weekend!`</span></span>
    
- <span data-ttu-id="e90a3-115">Michael Affronti 的一篇博客文章，其中显示与最后两个活动相同的 **ownerID** 5015012。</span><span class="sxs-lookup"><span data-stu-id="e90a3-115">A blog post by Michael Affronti, showing the same **ownerID** of 5015012 as the last two activities.</span></span> <span data-ttu-id="e90a3-116">此活动指定 **publisherVariable** 和 **linkVariable** 类型的两个模板变量。</span><span class="sxs-lookup"><span data-stu-id="e90a3-116">This activity specifies two template variables of type **publisherVariable** and **linkVariable**.</span></span> <span data-ttu-id="e90a3-117">**publisherVariable** 指定发布活动源项目的人 **，linkVariable** 包括由 **linkVariable**) 的名称、**文本** 和 **值** 子元素指定的有关该博客文章的详细信息 () 。</span><span class="sxs-lookup"><span data-stu-id="e90a3-117">**publisherVariable** specifies the person who published the activity feed item, and **linkVariable** includes further information (specified by the **name**, **text**, and **value** child elements of **linkVariable**) about the blog post.</span></span>
    
<span data-ttu-id="e90a3-118">这四个活动都指定了一个 **templateID** 值，该值与 **templates** 元素指定的三个模板之一匹配。</span><span class="sxs-lookup"><span data-stu-id="e90a3-118">Each of the four activities specifies a **templateID** value, which matches one of the three templates specified by the **templates** element.</span></span> <span data-ttu-id="e90a3-119">每个模板位于其自己的 **activityTemplateContainer** 元素中，由 **templateID** 值标识，该元素还用于显示具有相同 **templateID** 值的活动。</span><span class="sxs-lookup"><span data-stu-id="e90a3-119">Each template is in its own **activityTemplateContainer** element, identified by a **templateID** value that is also used to display an activity that has the same **templateID** value.</span></span> 
  
<span data-ttu-id="e90a3-120">有关示例中使用的 XML 元素的详细说明，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e90a3-120">For a detailed description of the XML elements used in the example, see the following topics:</span></span> 
  
- [<span data-ttu-id="e90a3-121">活动源项的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="e90a3-121">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)
    
- [<span data-ttu-id="e90a3-122">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="e90a3-122">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="e90a3-123">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="e90a3-123">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="e90a3-124">模板变量</span><span class="sxs-lookup"><span data-stu-id="e90a3-124">Template Variables</span></span>](template-variables.md)
    
## <a name="xml-example"></a><span data-ttu-id="e90a3-125">XML 示例</span><span class="sxs-lookup"><span data-stu-id="e90a3-125">XML example</span></span>

<span data-ttu-id="e90a3-126">以下示例显示包含四个 **活动的 activityFeed** XML：两个配置文件图片更新、一个状态更新和一个博客文章。</span><span class="sxs-lookup"><span data-stu-id="e90a3-126">The following example shows the **activityFeed** XML of four activities: two profile picture updates, a status update, and a blog post.</span></span> <span data-ttu-id="e90a3-127">XML 还指定用于显示相应活动的三个活动显示模板。</span><span class="sxs-lookup"><span data-stu-id="e90a3-127">The XML also specifies three activity display templates for displaying the corresponding activities.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="e90a3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e90a3-128">See also</span></span>

- [<span data-ttu-id="e90a3-129">OSC 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e90a3-129">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="e90a3-130">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="e90a3-130">XML for Activities</span></span>](xml-for-activities.md) 
- [<span data-ttu-id="e90a3-131">Capabilities XML 示例</span><span class="sxs-lookup"><span data-stu-id="e90a3-131">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="e90a3-132">好友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e90a3-132">Friends XML Example</span></span>](friends-xml-example.md)
- [<span data-ttu-id="e90a3-133">OutlookSocial Connector Provider XML 架构</span><span class="sxs-lookup"><span data-stu-id="e90a3-133">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

