---
title: 调试提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2dfaeed-7635-4c6b-9c35-b955ca1a85e9
description: '您可以通过多种方式来调试 Outlook Social Connector (.osc) 提供程序:'
ms.openlocfilehash: 39deb7b6c0b11460826bdbf1957ffd8404d926e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281067"
---
# <a name="debugging-a-provider"></a><span data-ttu-id="bffca-103">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="bffca-103">Debugging a provider</span></span>

<span data-ttu-id="bffca-104">您可以通过多种方式来调试 Outlook Social Connector (.osc) 提供程序:</span><span class="sxs-lookup"><span data-stu-id="bffca-104">There are several ways you can debug an Outlook Social Connector (OSC) provider:</span></span> 
  
- <span data-ttu-id="bffca-105">通过在 Outlook 或支持的 office 客户端应用程序的 office 熟知用户界面的功能区组件中使用调试命令, 可以使 .osc 执行各种操作。</span><span class="sxs-lookup"><span data-stu-id="bffca-105">By using debug commands in the ribbon component of the Office Fluent user interface in Outlook or the supporting Office client application to cause the OSC to take various actions.</span></span>
    
- <span data-ttu-id="bffca-106">通过使用 Fiddler 跟踪在社交网络及其 .osc 提供程序之间发送的 API 调用和 XML</span><span class="sxs-lookup"><span data-stu-id="bffca-106">By using Fiddler to trace API calls and XML sent between a social network and its OSC provider</span></span>
    
## <a name="debug-buttons"></a><span data-ttu-id="bffca-107">调试按钮</span><span class="sxs-lookup"><span data-stu-id="bffca-107">Debug buttons</span></span>

<span data-ttu-id="bffca-108">.osc 提供程序扩展性提供了调试 .osc 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="bffca-108">The OSC provider extensibility provides the capability of debugging an OSC provider.</span></span> <span data-ttu-id="bffca-109">若要调试提供程序, 请`DebugProviders`在注册表`SocialConnector`项下的 Windows 注册表中创建一个 DWORD 类型的值 (如下面的行所示), `DebugProviders`并将值设置为1。</span><span class="sxs-lookup"><span data-stu-id="bffca-109">To debug a provider, create a  `DebugProviders` value of type DWORD in the Windows registry under the  `SocialConnector` key (as shown in the following line), and set the  `DebugProviders` value to 1.</span></span> 
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`
  
<span data-ttu-id="bffca-110">默认情况下, 提供程序调试处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="bffca-110">By default, provider debugging is off.</span></span> <span data-ttu-id="bffca-111">如果`DebugProviders`值不存在或存在, 并且设置为值 0, 则表示提供程序调试处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="bffca-111">If the  `DebugProviders` value is not present, or it is present and set to a value of 0, provider debugging is turned off.</span></span> 
  
<span data-ttu-id="bffca-112">如果启用了提供程序调试, 则在发生错误时, .osc 将显示一个警报对话框, 其中包含详细错误信息, 并针对 .osc 提供程序 xml 架构验证任何 .osc 提供程序 xml。</span><span class="sxs-lookup"><span data-stu-id="bffca-112">If provider debugging is turned on, the OSC displays an alert dialog box with verbose error information when an error occurs, and validates any OSC provider XML against the OSC provider XML schema.</span></span> <span data-ttu-id="bffca-113">根据为 XML 字符串指定的命名空间, 使用 .osc 1.0 开发的 .osc 提供程序将针对 .osc 1.0 架构文件 OutlookSocialProvider 进行验证。</span><span class="sxs-lookup"><span data-stu-id="bffca-113">Based on the namespace specified for an XML string, an OSC provider developed by using OSC 1.0 is validated against the OSC 1.0 schema file, OutlookSocialProvider.xsd.</span></span> <span data-ttu-id="bffca-114">使用 .osc 1.1 或更高版本开发的一个 .osc 提供程序针对架构文件 outlooksocialprovider_ 1.1 进行了验证。</span><span class="sxs-lookup"><span data-stu-id="bffca-114">An OSC provider developed by using OSC 1.1 or later is validated against the schema file, OutlookSocialProvider_1.1.xsd.</span></span> <span data-ttu-id="bffca-115">使用此`DebugProviders`值时, 将对所有已加载的提供程序 (而不是特定的提供程序) 显示调试警报。</span><span class="sxs-lookup"><span data-stu-id="bffca-115">When you use the  `DebugProviders` value, the debug alert appears for all loaded providers instead of a specific provider.</span></span> 
  
<span data-ttu-id="bffca-116">若要显示可帮助您调试提供程序的调试按钮, 请`ShowDebugButtons`在注册表`SocialConnector`项下的 Windows 注册表中创建一个 DWORD 类型的值, `ShowDebugButtons`并将值设置为1。</span><span class="sxs-lookup"><span data-stu-id="bffca-116">To display debug buttons that can help you debug a provider, create a  `ShowDebugButtons` value of type DWORD in the Windows registry under the  `SocialConnector` key, and set the  `ShowDebugButtons` value to 1.</span></span> <span data-ttu-id="bffca-117">若要隐藏调试命令栏按钮, 请将`ShowDebugButtons`该值设置为0。</span><span class="sxs-lookup"><span data-stu-id="bffca-117">To hide the debug command bar buttons, set the  `ShowDebugButtons` value to 0.</span></span> 
  
<span data-ttu-id="bffca-118">对于 Outlook 2010 和自 Office 2013 之后的客户端应用程序, "调试" 按钮将显示在浏览器功能区的 "**加载项**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="bffca-118">For Outlook 2010 and client applications since Office 2013, the debug buttons appear on the **Add-ins** tab of the explorer ribbon.</span></span> <span data-ttu-id="bffca-119">对于 outlook 2007 和 outlook 2003, 调试按钮显示在 Outlook 资源管理器窗口的标准命令栏上。</span><span class="sxs-lookup"><span data-stu-id="bffca-119">For Outlook 2007 and Outlook 2003, the debug buttons appear on the standard command bar of the Outlook explorer window.</span></span> 
  
<span data-ttu-id="bffca-120">下表介绍了调试按钮。</span><span class="sxs-lookup"><span data-stu-id="bffca-120">The following table describes the debug buttons.</span></span>
  
|<span data-ttu-id="bffca-121">**调试按钮**</span><span class="sxs-lookup"><span data-stu-id="bffca-121">**Debug button**</span></span>|<span data-ttu-id="bffca-122">**Function**</span><span class="sxs-lookup"><span data-stu-id="bffca-122">**Function**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bffca-123">同步联系人</span><span class="sxs-lookup"><span data-stu-id="bffca-123">Sync Contacts</span></span>  <br/> |<span data-ttu-id="bffca-124">使 .osc 仅为缓存的联系人请求 .osc 提供程序。</span><span class="sxs-lookup"><span data-stu-id="bffca-124">Causes the OSC to ask the OSC provider for cached contacts only.</span></span>  <br/> |
|<span data-ttu-id="bffca-125">GAL 同步</span><span class="sxs-lookup"><span data-stu-id="bffca-125">GAL Sync</span></span>  <br/> |<span data-ttu-id="bffca-126">使 .osc 向 Outlook 联系人填充 Exchange 全局地址列表中的数据。</span><span class="sxs-lookup"><span data-stu-id="bffca-126">Causes the OSC to populate data from the Exchange Global Address List to Outlook contacts.</span></span>  <br/> |
|<span data-ttu-id="bffca-127">使类别缓存无效</span><span class="sxs-lookup"><span data-stu-id="bffca-127">Invalidate Category Cache</span></span>  <br/> |<span data-ttu-id="bffca-128">使 .osc 在刷新活动源时重新加载每个存储的类别列表。</span><span class="sxs-lookup"><span data-stu-id="bffca-128">Causes the OSC to reload the category list for each store when the activity feed is refreshed.</span></span>  <br/> |
   
## <a name="fiddler"></a><span data-ttu-id="bffca-129">Fiddler</span><span class="sxs-lookup"><span data-stu-id="bffca-129">Fiddler</span></span>

<span data-ttu-id="bffca-130">Fiddler 是一种调试工具, 用于检查从提供商发送到社交网络的 API 调用, 以及由社交网络发送给提供程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="bffca-130">Fiddler is an over-the-wire debugging tool to check the API calls sent from your provider to the social network, and XML sent by the social network to your provider.</span></span> <span data-ttu-id="bffca-131">Fiddler 可在[Fiddler Web 调试代理](https://www.fiddler2.com/fiddler2/version.asp)中进行下载。</span><span class="sxs-lookup"><span data-stu-id="bffca-131">Fiddler is available for download at [Fiddler Web Debugging Proxy](https://www.fiddler2.com/fiddler2/version.asp).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bffca-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bffca-132">See also</span></span>

- [<span data-ttu-id="bffca-133">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="bffca-133">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)  
- [<span data-ttu-id="bffca-134">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="bffca-134">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="bffca-135">开发提供程序的最佳实践</span><span class="sxs-lookup"><span data-stu-id="bffca-135">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
- [<span data-ttu-id="bffca-136">.osc 典型调用序列</span><span class="sxs-lookup"><span data-stu-id="bffca-136">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)  
- [<span data-ttu-id="bffca-137">使用 .osc XML 架构开发提供程序</span><span class="sxs-lookup"><span data-stu-id="bffca-137">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)  
- [<span data-ttu-id="bffca-138">准备发布一个 .osc 提供程序</span><span class="sxs-lookup"><span data-stu-id="bffca-138">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

