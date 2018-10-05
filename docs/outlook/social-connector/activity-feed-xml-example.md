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
# <a name="activity-feed-xml-example"></a><span data-ttu-id="eb08f-103">活动源的 XML 示例</span><span class="sxs-lookup"><span data-stu-id="eb08f-103">Activity Feed XML Example</span></span>

<span data-ttu-id="eb08f-104">本主题中的 XML 示例为活动源后它为社交网络调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)方法返回 Outlook Social Connector (OSC) 到的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="eb08f-104">The XML example in this topic is an activity feed XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method for a social network.</span></span> 
  
<span data-ttu-id="eb08f-105">该示例演示**activityFeed**包含以下四个活动的 XML，每个分隔**activityDetails**元素和匹配的模板显示目的：</span><span class="sxs-lookup"><span data-stu-id="eb08f-105">The example shows the **activityFeed** XML that contains the following four activities, each delimited by the **activityDetails** element and matching a template for display purposes:</span></span> 
  
- <span data-ttu-id="eb08f-106">通过 Melissa Macbeth，其**ownerID**社交网络上是 4667647 更新配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="eb08f-106">A profile picture update by Melissa Macbeth, whose **ownerID** on the social network is 4667647.</span></span> <span data-ttu-id="eb08f-107">此活动指定三个模板变量类型**publisherVariable**、 **listVariable**，和**pictureVariable** （这在**listVariable**括起来）。</span><span class="sxs-lookup"><span data-stu-id="eb08f-107">This activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable** (which is enclosed in **listVariable**).</span></span> <span data-ttu-id="eb08f-108">这些变量指定发布活动源项目，并图片 （通过使用**pictureVariable**的**名称**、**值**、 **altText**和**href**子元素） 更新的信息的人员。</span><span class="sxs-lookup"><span data-stu-id="eb08f-108">These variables specify the person who published the activity feed item, and information for the picture to be updated (by using the **name**, **value**, **altText**, and **href** child elements of **pictureVariable**).</span></span>
    
- <span data-ttu-id="eb08f-109">通过在社交网络其**ownerID**是 5015012 Michael Affronti 更新配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="eb08f-109">A profile picture update by Michael Affronti whose **ownerID** on the social network is 5015012.</span></span> <span data-ttu-id="eb08f-110">最后一次活动类似，此活动指定类型**publisherVariable**、 **listVariable**和**pictureVariable**的三个模板变量。</span><span class="sxs-lookup"><span data-stu-id="eb08f-110">Similar to the last activity, this activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable**.</span></span> <span data-ttu-id="eb08f-111">这些变量指定发布活动源项目和图片要更新的信息的人员。</span><span class="sxs-lookup"><span data-stu-id="eb08f-111">These variables specify the person who published the activity feed item and information for the picture to be updated.</span></span>
    
- <span data-ttu-id="eb08f-112">通过 Michael Affronti，显示同一**ownerID** 5015012 的最后一次活动为状态更新。</span><span class="sxs-lookup"><span data-stu-id="eb08f-112">A status update by Michael Affronti, showing the same **ownerID** of 5015012 as the last activity.</span></span> <span data-ttu-id="eb08f-113">此活动指定两个模板的变量类型**publisherVariable**和**textVariable**。</span><span class="sxs-lookup"><span data-stu-id="eb08f-113">This activity specifies two template variables of type **publisherVariable** and **textVariable**.</span></span> <span data-ttu-id="eb08f-114">**publisherVariable**指定用户发布的活动源项目，并**textVariable**包括状态行**值**`is hiking on Mount Rainier this weekend!`</span><span class="sxs-lookup"><span data-stu-id="eb08f-114">**publisherVariable** specifies the person who published the activity feed item, and **textVariable** includes a **value** of the status line  `is hiking on Mount Rainier this weekend!`</span></span>
    
- <span data-ttu-id="eb08f-115">Michael Affronti，显示同一**ownerID**的 5015012 作为最后两个活动的博客文章。</span><span class="sxs-lookup"><span data-stu-id="eb08f-115">A blog post by Michael Affronti, showing the same **ownerID** of 5015012 as the last two activities.</span></span> <span data-ttu-id="eb08f-116">此活动指定两个模板的变量类型**publisherVariable**和**linkVariable**。</span><span class="sxs-lookup"><span data-stu-id="eb08f-116">This activity specifies two template variables of type **publisherVariable** and **linkVariable**.</span></span> <span data-ttu-id="eb08f-117">**publisherVariable**指定用户发布的活动订阅源，并**linkVariable**进一步包括 （由**linkVariable**的**名称**、**文本**和**值**子元素指定） 的信息有关的博客文章。</span><span class="sxs-lookup"><span data-stu-id="eb08f-117">**publisherVariable** specifies the person who published the activity feed item, and **linkVariable** includes further information (specified by the **name**, **text**, and **value** child elements of **linkVariable**) about the blog post.</span></span>
    
<span data-ttu-id="eb08f-118">指定一个**templateID**值，该值匹配**模板**元素所指定的三个模板的一个每四个活动。</span><span class="sxs-lookup"><span data-stu-id="eb08f-118">Each of the four activities specifies a **templateID** value, which matches one of the three templates specified by the **templates** element.</span></span> <span data-ttu-id="eb08f-119">每个模板都由一个**templateID**值，也可用于显示活动具有相同的**templateID**值标识自己**activityTemplateContainer**元素中。</span><span class="sxs-lookup"><span data-stu-id="eb08f-119">Each template is in its own **activityTemplateContainer** element, identified by a **templateID** value that is also used to display an activity that has the same **templateID** value.</span></span> 
  
<span data-ttu-id="eb08f-120">在示例中使用的 XML 元素的详细说明，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="eb08f-120">For a detailed description of the XML elements used in the example, see the following topics:</span></span> 
  
- [<span data-ttu-id="eb08f-121">概述 XML 的活动订阅源</span><span class="sxs-lookup"><span data-stu-id="eb08f-121">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)
    
- [<span data-ttu-id="eb08f-122">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="eb08f-122">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="eb08f-123">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="eb08f-123">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="eb08f-124">模板变量</span><span class="sxs-lookup"><span data-stu-id="eb08f-124">Template Variables</span></span>](template-variables.md)
    
## <a name="xml-example"></a><span data-ttu-id="eb08f-125">XML 示例</span><span class="sxs-lookup"><span data-stu-id="eb08f-125">XML example</span></span>

<span data-ttu-id="eb08f-126">下面的示例演示**activityFeed**四项活动的 XML： 两个配置文件图片更新、 状态更新和博客文章。</span><span class="sxs-lookup"><span data-stu-id="eb08f-126">The following example shows the **activityFeed** XML of four activities: two profile picture updates, a status update, and a blog post.</span></span> <span data-ttu-id="eb08f-127">XML 还会指定用于显示相应的活动的三个活动显示模板。</span><span class="sxs-lookup"><span data-stu-id="eb08f-127">The XML also specifies three activity display templates for displaying the corresponding activities.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="eb08f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb08f-128">See also</span></span>

- [<span data-ttu-id="eb08f-129">OSC 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="eb08f-129">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="eb08f-130">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="eb08f-130">XML for Activities</span></span>](xml-for-activities.md) 
- [<span data-ttu-id="eb08f-131">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="eb08f-131">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="eb08f-132">朋友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="eb08f-132">Friends XML Example</span></span>](friends-xml-example.md)
- [<span data-ttu-id="eb08f-133">Outlook Social Connector 提供程序的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="eb08f-133">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

