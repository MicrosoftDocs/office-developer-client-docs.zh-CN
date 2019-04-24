---
title: 活动源 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa50ca36-8d01-4770-9d9c-30a5baa146ff
description: '本主题中的 XML 示例是在为社交网络调用 ISocialSession2:: GetActivitiesEx 方法后返回到 Outlook Social Connector (.osc) 的活动源 XML 字符串。'
ms.openlocfilehash: 6370b559c5160bfa48d32afa77715e9a7c126aab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281330"
---
# <a name="activity-feed-xml-example"></a><span data-ttu-id="746e3-103">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="746e3-103">Activity Feed XML Example</span></span>

<span data-ttu-id="746e3-104">本主题中的 XML 示例是在为社交网络调用[ISocialSession2:: GetActivitiesEx](isocialsession2-getactivitiesex.md)方法后返回到 Outlook Social Connector (.osc) 的活动源 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="746e3-104">The XML example in this topic is an activity feed XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md) method for a social network.</span></span> 
  
<span data-ttu-id="746e3-105">该示例显示包含以下四个活动的**microsoft.office.server.activityfeed** XML, 每个活动都由**activityDetails**元素分隔并匹配用于显示目的的模板:</span><span class="sxs-lookup"><span data-stu-id="746e3-105">The example shows the **activityFeed** XML that contains the following four activities, each delimited by the **activityDetails** element and matching a template for display purposes:</span></span> 
  
- <span data-ttu-id="746e3-106">由 Melissa Macbeth 的配置文件图片更新, 其在社交网络上的**ownerID**为4667647。</span><span class="sxs-lookup"><span data-stu-id="746e3-106">A profile picture update by Melissa Macbeth, whose **ownerID** on the social network is 4667647.</span></span> <span data-ttu-id="746e3-107">此活动指定**publisherVariable**、 **listVariable**和**pictureVariable**类型的三个模板变量 (包含在**listVariable**中)。</span><span class="sxs-lookup"><span data-stu-id="746e3-107">This activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable** (which is enclosed in **listVariable**).</span></span> <span data-ttu-id="746e3-108">这些变量指定发布活动源项目的人员, 以及要更新的图片的信息 (使用**pictureVariable**的**name**、 **value**、 **altText**和**href**子元素)。</span><span class="sxs-lookup"><span data-stu-id="746e3-108">These variables specify the person who published the activity feed item, and information for the picture to be updated (by using the **name**, **value**, **altText**, and **href** child elements of **pictureVariable**).</span></span>
    
- <span data-ttu-id="746e3-109">由 Michael Affronti 的配置文件图片更新, 其社会网络上的**ownerID**为5015012。</span><span class="sxs-lookup"><span data-stu-id="746e3-109">A profile picture update by Michael Affronti whose **ownerID** on the social network is 5015012.</span></span> <span data-ttu-id="746e3-110">与最后一个活动类似, 此活动指定**publisherVariable**、 **listVariable**和**pictureVariable**类型的三个模板变量。</span><span class="sxs-lookup"><span data-stu-id="746e3-110">Similar to the last activity, this activity specifies three template variables of type **publisherVariable**, **listVariable**, and **pictureVariable**.</span></span> <span data-ttu-id="746e3-111">这些变量指定发布活动源项目的人员以及要更新的图片的信息。</span><span class="sxs-lookup"><span data-stu-id="746e3-111">These variables specify the person who published the activity feed item and information for the picture to be updated.</span></span>
    
- <span data-ttu-id="746e3-112">迈克尔• Affronti 的状态更新, 显示与最后一个活动相同的 5015012 **ownerID** 。</span><span class="sxs-lookup"><span data-stu-id="746e3-112">A status update by Michael Affronti, showing the same **ownerID** of 5015012 as the last activity.</span></span> <span data-ttu-id="746e3-113">此活动指定**publisherVariable**和**textVariable**类型的两个模板变量。</span><span class="sxs-lookup"><span data-stu-id="746e3-113">This activity specifies two template variables of type **publisherVariable** and **textVariable**.</span></span> <span data-ttu-id="746e3-114">**publisherVariable**指定发布活动源项目的人员, 并**textVariable**包含状态行的**值**`is hiking on Mount Rainier this weekend!`</span><span class="sxs-lookup"><span data-stu-id="746e3-114">**publisherVariable** specifies the person who published the activity feed item, and **textVariable** includes a **value** of the status line  `is hiking on Mount Rainier this weekend!`</span></span>
    
- <span data-ttu-id="746e3-115">迈克尔• Affronti 中的博客文章, 显示与最后两个活动相同的 5015012 **ownerID** 。</span><span class="sxs-lookup"><span data-stu-id="746e3-115">A blog post by Michael Affronti, showing the same **ownerID** of 5015012 as the last two activities.</span></span> <span data-ttu-id="746e3-116">此活动指定**publisherVariable**和**linkVariable**类型的两个模板变量。</span><span class="sxs-lookup"><span data-stu-id="746e3-116">This activity specifies two template variables of type **publisherVariable** and **linkVariable**.</span></span> <span data-ttu-id="746e3-117">**publisherVariable**指定发布活动源项目的人员, 并**linkVariable**包含详细信息 (由**linkVariable**的**name**、 **text**和**value**子元素指定)关于博客文章。</span><span class="sxs-lookup"><span data-stu-id="746e3-117">**publisherVariable** specifies the person who published the activity feed item, and **linkVariable** includes further information (specified by the **name**, **text**, and **value** child elements of **linkVariable**) about the blog post.</span></span>
    
<span data-ttu-id="746e3-118">这四个活动中的每一个都指定一个**templateID**值, 该值与**templates**元素指定的三个模板之一相匹配。</span><span class="sxs-lookup"><span data-stu-id="746e3-118">Each of the four activities specifies a **templateID** value, which matches one of the three templates specified by the **templates** element.</span></span> <span data-ttu-id="746e3-119">每个模板都位于其自己的**activityTemplateContainer**元素中, 该元素由另一个**templateID**值标识, 该值也用于显示具有相同**templateID**值的活动。</span><span class="sxs-lookup"><span data-stu-id="746e3-119">Each template is in its own **activityTemplateContainer** element, identified by a **templateID** value that is also used to display an activity that has the same **templateID** value.</span></span> 
  
<span data-ttu-id="746e3-120">有关本示例中使用的 XML 元素的详细说明, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="746e3-120">For a detailed description of the XML elements used in the example, see the following topics:</span></span> 
  
- [<span data-ttu-id="746e3-121">活动源项目的 XML 概述</span><span class="sxs-lookup"><span data-stu-id="746e3-121">Overview of XML for an Activity Feed Item</span></span>](overview-of-xml-for-an-activity-feed-item.md)
    
- [<span data-ttu-id="746e3-122">activityDetails 元素</span><span class="sxs-lookup"><span data-stu-id="746e3-122">activityDetails Element</span></span>](activitydetails-element.md)
    
- [<span data-ttu-id="746e3-123">activityTemplateContainer 元素</span><span class="sxs-lookup"><span data-stu-id="746e3-123">activityTemplateContainer Element</span></span>](activitytemplatecontainer-element.md)
    
- [<span data-ttu-id="746e3-124">模板变量</span><span class="sxs-lookup"><span data-stu-id="746e3-124">Template Variables</span></span>](template-variables.md)
    
## <a name="xml-example"></a><span data-ttu-id="746e3-125">XML 示例</span><span class="sxs-lookup"><span data-stu-id="746e3-125">XML example</span></span>

<span data-ttu-id="746e3-126">以下示例显示了四个活动的**microsoft.office.server.activityfeed** XML: 两个配置文件图片更新、一个状态更新和一个博客文章。</span><span class="sxs-lookup"><span data-stu-id="746e3-126">The following example shows the **activityFeed** XML of four activities: two profile picture updates, a status update, and a blog post.</span></span> <span data-ttu-id="746e3-127">XML 还指定三个活动显示模板, 用于显示相应的活动。</span><span class="sxs-lookup"><span data-stu-id="746e3-127">The XML also specifies three activity display templates for displaying the corresponding activities.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="746e3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="746e3-128">See also</span></span>

- [<span data-ttu-id="746e3-129">.osc 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="746e3-129">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="746e3-130">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="746e3-130">XML for Activities</span></span>](xml-for-activities.md) 
- [<span data-ttu-id="746e3-131">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="746e3-131">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="746e3-132">友元 XML 示例</span><span class="sxs-lookup"><span data-stu-id="746e3-132">Friends XML Example</span></span>](friends-xml-example.md)
- [<span data-ttu-id="746e3-133">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="746e3-133">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

