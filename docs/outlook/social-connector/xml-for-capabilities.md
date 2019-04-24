---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: '(.osc) 提供程序 XML 架构中的 "功能" 元素允许 .osc 提供程序指定其功能。 此类功能包括以下内容:'
ms.openlocfilehash: ff6abbd4d99eb542a11e3d64a2015fc0585fca79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356441"
---
# <a name="xml-for-capabilities"></a><span data-ttu-id="78145-104">功能的 XML</span><span class="sxs-lookup"><span data-stu-id="78145-104">XML for capabilities</span></span>

<span data-ttu-id="78145-105">(.osc) 提供程序 XML 架构中的 "**功能**" 元素允许 .osc 提供程序指定其功能。</span><span class="sxs-lookup"><span data-stu-id="78145-105">The **capabilities** element in the (OSC) provider XML schema allows an OSC provider to specify its functionality.</span></span> <span data-ttu-id="78145-106">此类功能包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="78145-106">Such functionality includes the following:</span></span> 
  
- <span data-ttu-id="78145-107">提供程序是否支持从社交网络获取、缓存或动态查找好友和活动。</span><span class="sxs-lookup"><span data-stu-id="78145-107">Whether the provider supports getting, caching, or dynamically looking up friends and activities from the social network.</span></span>
    
- <span data-ttu-id="78145-108">.osc 应如何显示某些登录用户界面。</span><span class="sxs-lookup"><span data-stu-id="78145-108">How the OSC should display certain logon user interfaces.</span></span>
    
- <span data-ttu-id="78145-109">.osc 是否应使用基于表单的身份验证, 或自动配置社交网络上的用户的社交网络和日志。</span><span class="sxs-lookup"><span data-stu-id="78145-109">Whether the OSC should use forms-based authentication or automatically configure the social network and logs on the user on the social network.</span></span>
    
<span data-ttu-id="78145-110">**功能**的 XML 架构非常关键, 因为它会将提供程序支持的功能标识为 .osc。</span><span class="sxs-lookup"><span data-stu-id="78145-110">The XML schema for **capabilities** is critical because it identifies to the OSC the functionality supported by the provider.</span></span> <span data-ttu-id="78145-111">一个 .osc 提供程序必须实现[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法, 该方法返回_结果_字符串。</span><span class="sxs-lookup"><span data-stu-id="78145-111">An OSC provider must implement the [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md) method that returns a  _result_ string.</span></span> <span data-ttu-id="78145-112">.osc 调用**ISocialProvider:: GetCapabilities**获取有关在_结果_字符串中的 .osc 提供程序的功能的信息, 该信息符合**功能**元素的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="78145-112">The OSC calls **ISocialProvider::GetCapabilities** to obtain information about the capabilities of the OSC provider in the  _result_ string, which complies with the XML schema definition for the **capabilities** element.</span></span> <span data-ttu-id="78145-113">此信息支持从 .osc 到 .osc 提供程序的后续呼叫正常运行。</span><span class="sxs-lookup"><span data-stu-id="78145-113">This information enables subsequent calls from the OSC to the OSC provider to operate correctly.</span></span> 
  
<span data-ttu-id="78145-114">若要将 .osc 提供程序的功能指定为**ISocialProvider:: GetCapabilities**方法的输出参数, 您必须符合 .osc 提供程序扩展性 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="78145-114">To specify capabilities of an OSC provider as an output parameter of the **ISocialProvider::GetCapabilities** method, you must conform to the OSC provider extensibility XML schema.</span></span> <span data-ttu-id="78145-115">下图显示了 XML 结构的**功能**。</span><span class="sxs-lookup"><span data-stu-id="78145-115">The following figure shows the **capabilities** XML structure.</span></span> 
  
<span data-ttu-id="78145-116">**图1。\<功能\> XML 结构**</span><span class="sxs-lookup"><span data-stu-id="78145-116">**Figure 1. \<capabilities\> XML structure**</span></span>

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
<span data-ttu-id="78145-118">有关 "**功能**" 元素的子元素的详细说明, 请参阅[功能 XML 元素](capabilities-xml-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="78145-118">For detailed descriptions of child elements of the **capabilities** element, see [Capabilities XML Elements](capabilities-xml-elements.md).</span></span> <span data-ttu-id="78145-119">有关 XML 的**功能**示例, 请参阅[功能 xml 示例](capabilities-xml-example.md)。</span><span class="sxs-lookup"><span data-stu-id="78145-119">For an example of **capabilities** XML, see [Capabilities XML Example](capabilities-xml-example.md).</span></span> <span data-ttu-id="78145-120">有关 .osc 提供程序 XML 架构的完整定义 (包括哪些元素是必需元素或可选的元素), 请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="78145-120">For a complete definition of the OSC provider XML schema, including which elements are required or optional, see [Outlook Social Connector Provider XML Schema](outlook-social-connector-provider-xml-schema.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="78145-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78145-121">See also</span></span>

- [<span data-ttu-id="78145-122">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="78145-122">Capabilities XML Example</span></span>](capabilities-xml-example.md)  
- [<span data-ttu-id="78145-123">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="78145-123">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)  
- [<span data-ttu-id="78145-124">适用于好友的 XML</span><span class="sxs-lookup"><span data-stu-id="78145-124">XML for Friends</span></span>](xml-for-friends.md)  
- [<span data-ttu-id="78145-125">适用于活动的 XML</span><span class="sxs-lookup"><span data-stu-id="78145-125">XML for Activities</span></span>](xml-for-activities.md)
- [<span data-ttu-id="78145-126">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="78145-126">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)

