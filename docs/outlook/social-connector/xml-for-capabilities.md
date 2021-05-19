---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: OSC (XML 架构) capabilities 元素允许 OSC 提供程序指定其功能。 此类功能包括：
ms.openlocfilehash: ff6abbd4d99eb542a11e3d64a2015fc0585fca79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435003"
---
# <a name="xml-for-capabilities"></a><span data-ttu-id="fbc2b-104">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="fbc2b-104">XML for capabilities</span></span>

<span data-ttu-id="fbc2b-105">OSC (XML 架构) **capabilities** 元素允许 OSC 提供程序指定其功能。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-105">The **capabilities** element in the (OSC) provider XML schema allows an OSC provider to specify its functionality.</span></span> <span data-ttu-id="fbc2b-106">此类功能包括：</span><span class="sxs-lookup"><span data-stu-id="fbc2b-106">Such functionality includes the following:</span></span> 
  
- <span data-ttu-id="fbc2b-107">提供程序是否支持从社交网络获取、缓存或动态查找好友和活动。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-107">Whether the provider supports getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="fbc2b-108">OSC 应如何显示某些登录用户界面。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-108">How the OSC should display certain logon user interfaces.</span></span>
    
- <span data-ttu-id="fbc2b-109">OSC 是应该使用基于表单的身份验证，还是自动配置社交网络和社交网络上的用户日志。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-109">Whether the OSC should use forms-based authentication or automatically configure the social network and logs on the user on the social network.</span></span>
    
<span data-ttu-id="fbc2b-110">功能的 XML **架构** 至关重要，因为它向 OSC 标识提供程序支持的功能。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-110">The XML schema for **capabilities** is critical because it identifies to the OSC the functionality supported by the provider.</span></span> <span data-ttu-id="fbc2b-111">OSC 提供程序必须实现返回结果字符串的 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)_方法。_</span><span class="sxs-lookup"><span data-stu-id="fbc2b-111">An OSC provider must implement the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that returns a  _result_ string.</span></span> <span data-ttu-id="fbc2b-112">OSC 调用 **ISocialProvider：：GetCapabilities** 以获取有关结果字符串中 OSC 提供程序的功能的信息，这符合 **capabilities** 元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-112">The OSC calls **ISocialProvider::GetCapabilities** to obtain information about the capabilities of the OSC provider in the  _result_ string, which complies with the XML schema definition for the **capabilities** element.</span></span> <span data-ttu-id="fbc2b-113">此信息使从 OSC 到 OSC 提供程序的后续调用能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-113">This information enables subsequent calls from the OSC to the OSC provider to operate correctly.</span></span> 
  
<span data-ttu-id="fbc2b-114">若要将 OSC 提供程序的功能指定为 **ISocialProvider：：GetCapabilities** 方法的输出参数，必须符合 OSC 提供程序扩展性 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-114">To specify capabilities of an OSC provider as an output parameter of the **ISocialProvider::GetCapabilities** method, you must conform to the OSC provider extensibility XML schema.</span></span> <span data-ttu-id="fbc2b-115">下图显示了 **功能** XML 结构。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-115">The following figure shows the **capabilities** XML structure.</span></span> 
  
<span data-ttu-id="fbc2b-116">**图 1. \<capabilities \> XML 结构**</span><span class="sxs-lookup"><span data-stu-id="fbc2b-116">**Figure 1. \<capabilities\> XML structure**</span></span>

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
<span data-ttu-id="fbc2b-118">有关 **capabilities** 元素的子元素的详细说明，请参阅 [Capabilities XML Elements。](capabilities-xml-elements.md)</span><span class="sxs-lookup"><span data-stu-id="fbc2b-118">For detailed descriptions of child elements of the **capabilities** element, see [Capabilities XML Elements](capabilities-xml-elements.md).</span></span> <span data-ttu-id="fbc2b-119">有关功能 XML **的示例** ，请参阅 [Capabilities XML Example](capabilities-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc2b-119">For an example of **capabilities** XML, see [Capabilities XML Example](capabilities-xml-example.md).</span></span> <span data-ttu-id="fbc2b-120">有关 OSC 提供程序 XML 架构的完整定义，包括哪些元素是必需的或可选的，请参阅Outlook[连接器提供程序 XML 架构。](outlook-social-connector-provider-xml-schema.md)</span><span class="sxs-lookup"><span data-stu-id="fbc2b-120">For a complete definition of the OSC provider XML schema, including which elements are required or optional, see [Outlook Social Connector Provider XML Schema](outlook-social-connector-provider-xml-schema.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fbc2b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbc2b-121">See also</span></span>

- [<span data-ttu-id="fbc2b-122">Capabilities XML 示例</span><span class="sxs-lookup"><span data-stu-id="fbc2b-122">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="fbc2b-123">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="fbc2b-123">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="fbc2b-124">好友 XML</span><span class="sxs-lookup"><span data-stu-id="fbc2b-124">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="fbc2b-125">活动的 XML</span><span class="sxs-lookup"><span data-stu-id="fbc2b-125">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="fbc2b-126">使用 OSC XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="fbc2b-126">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

