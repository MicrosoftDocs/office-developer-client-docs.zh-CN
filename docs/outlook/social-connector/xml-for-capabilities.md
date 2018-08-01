---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: Capabilities 元素 (OSC) 提供程序的 XML 架构中允许 OSC 提供程序指定其功能。 此类功能包括以下组件：
ms.openlocfilehash: 8192c4d559ae656cfc3b12cd8f50f7d4acd5ed5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779330"
---
# <a name="xml-for-capabilities"></a><span data-ttu-id="1be38-104">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="1be38-104">XML for capabilities</span></span>

<span data-ttu-id="1be38-105">**Capabilities**元素 (OSC) 提供程序的 XML 架构中允许 OSC 提供程序指定其功能。</span><span class="sxs-lookup"><span data-stu-id="1be38-105">The **capabilities** element in the (OSC) provider XML schema allows an OSC provider to specify its functionality.</span></span> <span data-ttu-id="1be38-106">此类功能包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="1be38-106">Such functionality includes the following:</span></span> 
  
- <span data-ttu-id="1be38-107">是否提供程序支持获取、 缓存，或动态查找朋友和活动从社交网络。</span><span class="sxs-lookup"><span data-stu-id="1be38-107">Whether the provider supports getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="1be38-108">如何 OSC 应显示特定登录用户界面。</span><span class="sxs-lookup"><span data-stu-id="1be38-108">How the OSC should display certain logon user interfaces.</span></span>
    
- <span data-ttu-id="1be38-109">是否 OSC 应该使用基于表单的身份验证或自动配置的社交网络和日志上社交网络上的用户。</span><span class="sxs-lookup"><span data-stu-id="1be38-109">Whether the OSC should use forms-based authentication or automatically configure the social network and logs on the user on the social network.</span></span>
    
<span data-ttu-id="1be38-110">**功能**的 XML 架构非常重要，因为它标识 OSC 提供程序支持的功能。</span><span class="sxs-lookup"><span data-stu-id="1be38-110">The XML schema for **capabilities** is critical because it identifies to the OSC the functionality supported by the provider.</span></span> <span data-ttu-id="1be38-111">OSC 提供程序必须实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法返回_结果_字符串。</span><span class="sxs-lookup"><span data-stu-id="1be38-111">An OSC provider must implement the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that returns a  _result_ string.</span></span> <span data-ttu-id="1be38-112">OSC 调用**ISocialProvider::GetCapabilities**获取 OSC 提供程序_结果_字符串，符合**capabilities**元素的 XML 架构定义中的功能有关的信息。</span><span class="sxs-lookup"><span data-stu-id="1be38-112">The OSC calls **ISocialProvider::GetCapabilities** to obtain information about the capabilities of the OSC provider in the  _result_ string, which complies with the XML schema definition for the **capabilities** element.</span></span> <span data-ttu-id="1be38-113">此信息允许对后续调用从 OSC OSC 提供程序才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="1be38-113">This information enables subsequent calls from the OSC to the OSC provider to operate correctly.</span></span> 
  
<span data-ttu-id="1be38-114">若要作为**ISocialProvider::GetCapabilities**方法的输出参数指定 OSC 提供程序的功能，必须符合 OSC 提供程序扩展性 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="1be38-114">To specify capabilities of an OSC provider as an output parameter of the **ISocialProvider::GetCapabilities** method, you must conform to the OSC provider extensibility XML schema.</span></span> <span data-ttu-id="1be38-115">下图显示了**功能**XML 结构。</span><span class="sxs-lookup"><span data-stu-id="1be38-115">The following figure shows the **capabilities** XML structure.</span></span> 
  
<span data-ttu-id="1be38-116">**图 1。\<功能\>XML 结构**</span><span class="sxs-lookup"><span data-stu-id="1be38-116">**Figure 1. \<capabilities\> XML structure**</span></span>

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
<span data-ttu-id="1be38-118">**Capabilities**元素的子元素的详细说明，请参阅[功能 XML 元素](capabilities-xml-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="1be38-118">For detailed descriptions of child elements of the **capabilities** element, see [Capabilities XML Elements](capabilities-xml-elements.md).</span></span> <span data-ttu-id="1be38-119">**功能**XML 的示例，请参阅[功能 XML 示例](capabilities-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="1be38-119">For an example of **capabilities** XML, see [Capabilities XML Example](capabilities-xml-example.md).</span></span> <span data-ttu-id="1be38-120">有关完整定义 OSC 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="1be38-120">For a complete definition of the OSC provider XML schema, including which elements are required or optional, see [Outlook Social Connector Provider XML Schema](outlook-social-connector-provider-xml-schema.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1be38-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1be38-121">See also</span></span>

- [<span data-ttu-id="1be38-122">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="1be38-122">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="1be38-123">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="1be38-123">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="1be38-124">朋友 XML</span><span class="sxs-lookup"><span data-stu-id="1be38-124">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="1be38-125">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="1be38-125">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="1be38-126">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="1be38-126">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

