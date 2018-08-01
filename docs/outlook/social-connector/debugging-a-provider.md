---
title: 调试提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2dfaeed-7635-4c6b-9c35-b955ca1a85e9
description: 有几种方法可以调试的 Outlook Social Connector (OSC) 提供程序：
ms.openlocfilehash: ada439ca3b038ca9a0e849b47ff6a5f54e5016f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779206"
---
# <a name="debugging-a-provider"></a><span data-ttu-id="db1c2-103">调试提供程序</span><span class="sxs-lookup"><span data-stu-id="db1c2-103">Debugging a provider</span></span>

<span data-ttu-id="db1c2-104">有几种方法可以调试的 Outlook Social Connector (OSC) 提供程序：</span><span class="sxs-lookup"><span data-stu-id="db1c2-104">There are several ways you can debug an Outlook Social Connector (OSC) provider:</span></span> 
  
- <span data-ttu-id="db1c2-105">通过使用 Outlook 或支持的 Office 客户端应用程序中的 Office Fluent 用户界面的功能区组件中调试命令导致 OSC 各种操作。</span><span class="sxs-lookup"><span data-stu-id="db1c2-105">By using debug commands in the ribbon component of the Office Fluent user interface in Outlook or the supporting Office client application to cause the OSC to take various actions.</span></span>
    
- <span data-ttu-id="db1c2-106">使用 Fiddler 跟踪 API 调用和社交网络和其 OSC 提供程序之间发送的 XML</span><span class="sxs-lookup"><span data-stu-id="db1c2-106">By using Fiddler to trace API calls and XML sent between a social network and its OSC provider</span></span>
    
## <a name="debug-buttons"></a><span data-ttu-id="db1c2-107">调试按钮</span><span class="sxs-lookup"><span data-stu-id="db1c2-107">Debug buttons</span></span>

<span data-ttu-id="db1c2-108">OSC 提供程序扩展性提供的调试 OSC 提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="db1c2-108">The OSC provider extensibility provides the capability of debugging an OSC provider.</span></span> <span data-ttu-id="db1c2-109">若要调试提供程序，创建`DebugProviders`的值在 Windows 注册表中键入 DWORD`SocialConnector`键 （如下面的行所示），并设置`DebugProviders`值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="db1c2-109">To debug a provider, create a  `DebugProviders` value of type DWORD in the Windows registry under the  `SocialConnector` key (as shown in the following line), and set the  `DebugProviders` value to 1.</span></span> 
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector`
  
<span data-ttu-id="db1c2-110">默认情况下，提供程序调试处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="db1c2-110">By default, provider debugging is off.</span></span> <span data-ttu-id="db1c2-111">如果`DebugProviders`值不存在，或存在但处于关闭状态设置为值为 0，调试提供程序。</span><span class="sxs-lookup"><span data-stu-id="db1c2-111">If the  `DebugProviders` value is not present, or it is present and set to a value of 0, provider debugging is turned off.</span></span> 
  
<span data-ttu-id="db1c2-112">如果已启用调试提供程序，OSC 将显示详细错误信息警报对话框时出错，发生此事件，并验证 OSC 提供程序的 XML 架构针对任何 OSC 提供程序 XML。</span><span class="sxs-lookup"><span data-stu-id="db1c2-112">If provider debugging is turned on, the OSC displays an alert dialog box with verbose error information when an error occurs, and validates any OSC provider XML against the OSC provider XML schema.</span></span> <span data-ttu-id="db1c2-113">基于指定的 XML 字符串的命名空间，针对 OSC 1.0 架构文件，OutlookSocialProvider.xsd 验证使用 OSC 1.0 开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="db1c2-113">Based on the namespace specified for an XML string, an OSC provider developed by using OSC 1.0 is validated against the OSC 1.0 schema file, OutlookSocialProvider.xsd.</span></span> <span data-ttu-id="db1c2-114">OSC 提供程序开发使用 OSC 1.1 或更高版本的架构文件，OutlookSocialProvider_1.1.xsd 针对验证。</span><span class="sxs-lookup"><span data-stu-id="db1c2-114">An OSC provider developed by using OSC 1.1 or later is validated against the schema file, OutlookSocialProvider_1.1.xsd.</span></span> <span data-ttu-id="db1c2-115">当您使用`DebugProviders`值，为所有已加载的提供程序，而不是特定提供程序将出现调试通知。</span><span class="sxs-lookup"><span data-stu-id="db1c2-115">When you use the  `DebugProviders` value, the debug alert appears for all loaded providers instead of a specific provider.</span></span> 
  
<span data-ttu-id="db1c2-116">若要显示可帮助您调试提供程序的调试按钮，创建`ShowDebugButtons`的值在 Windows 注册表中键入 DWORD`SocialConnector`键，并设置`ShowDebugButtons`值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="db1c2-116">To display debug buttons that can help you debug a provider, create a  `ShowDebugButtons` value of type DWORD in the Windows registry under the  `SocialConnector` key, and set the  `ShowDebugButtons` value to 1.</span></span> <span data-ttu-id="db1c2-117">若要隐藏调试命令栏按钮，将`ShowDebugButtons`为 0 的值。</span><span class="sxs-lookup"><span data-stu-id="db1c2-117">To hide the debug command bar buttons, set the  `ShowDebugButtons` value to 0.</span></span> 
  
<span data-ttu-id="db1c2-118">有关 Outlook 2010 和相 Office 2013 的客户端应用程序，调试按钮显示在资源管理器功能区的**加载项**选项卡上。</span><span class="sxs-lookup"><span data-stu-id="db1c2-118">For Outlook 2010 and client applications since Office 2013, the debug buttons appear on the **Add-ins** tab of the explorer ribbon.</span></span> <span data-ttu-id="db1c2-119">对于 Outlook 2007 和 Outlook 2003，调试按钮显示在 Outlook 资源管理器窗口的标准命令栏上。</span><span class="sxs-lookup"><span data-stu-id="db1c2-119">For Outlook 2007 and Outlook 2003, the debug buttons appear on the standard command bar of the Outlook explorer window.</span></span> 
  
<span data-ttu-id="db1c2-120">下表介绍调试按钮。</span><span class="sxs-lookup"><span data-stu-id="db1c2-120">The following table describes the debug buttons.</span></span>
  
|<span data-ttu-id="db1c2-121">**调试按钮**</span><span class="sxs-lookup"><span data-stu-id="db1c2-121">**Debug button**</span></span>|<span data-ttu-id="db1c2-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="db1c2-122">**Function**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db1c2-123">同步联系人</span><span class="sxs-lookup"><span data-stu-id="db1c2-123">Sync Contacts</span></span>  <br/> |<span data-ttu-id="db1c2-124">使 OSC 寻求仅缓存联系人 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="db1c2-124">Causes the OSC to ask the OSC provider for cached contacts only.</span></span>  <br/> |
|<span data-ttu-id="db1c2-125">GAL 同步</span><span class="sxs-lookup"><span data-stu-id="db1c2-125">GAL Sync</span></span>  <br/> |<span data-ttu-id="db1c2-126">使 OSC 填充到 Outlook 联系人从 Exchange 全球通讯簿数据。</span><span class="sxs-lookup"><span data-stu-id="db1c2-126">Causes the OSC to populate data from the Exchange Global Address List to Outlook contacts.</span></span>  <br/> |
|<span data-ttu-id="db1c2-127">使无效类别缓存</span><span class="sxs-lookup"><span data-stu-id="db1c2-127">Invalidate Category Cache</span></span>  <br/> |<span data-ttu-id="db1c2-128">使 OSC 时刷新活动源重新加载类别列表中的每个存储区。</span><span class="sxs-lookup"><span data-stu-id="db1c2-128">Causes the OSC to reload the category list for each store when the activity feed is refreshed.</span></span>  <br/> |
   
## <a name="fiddler"></a><span data-ttu-id="db1c2-129">Fiddler</span><span class="sxs-lookup"><span data-stu-id="db1c2-129">Fiddler</span></span>

<span data-ttu-id="db1c2-130">Fiddler 是线上调试工具检查的 API 调用从您的提供商发送到社交网络和社交网络发送到您的提供程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="db1c2-130">Fiddler is an over-the-wire debugging tool to check the API calls sent from your provider to the social network, and XML sent by the social network to your provider.</span></span> <span data-ttu-id="db1c2-131">Fiddler 仅供以下位置下载： [Fiddler Web 调试代理](http://www.fiddler2.com/fiddler2/version.asp)。</span><span class="sxs-lookup"><span data-stu-id="db1c2-131">Fiddler is available for download at [Fiddler Web Debugging Proxy](http://www.fiddler2.com/fiddler2/version.asp).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db1c2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db1c2-132">See also</span></span>

- [<span data-ttu-id="db1c2-133">快速学习开发提供程序的步骤</span><span class="sxs-lookup"><span data-stu-id="db1c2-133">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)  
- [<span data-ttu-id="db1c2-134">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="db1c2-134">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md) 
- [<span data-ttu-id="db1c2-135">开发提供程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="db1c2-135">Best Practices for Developing a Provider</span></span>](best-practices-for-developing-a-provider.md)
- [<span data-ttu-id="db1c2-136">OSC 典型调用序列 （英文)</span><span class="sxs-lookup"><span data-stu-id="db1c2-136">OSC Typical Calling Sequences</span></span>](osc-typical-calling-sequences.md)  
- [<span data-ttu-id="db1c2-137">开发 OSC XML 架构的提供程序</span><span class="sxs-lookup"><span data-stu-id="db1c2-137">Developing a Provider with the OSC XML Schema</span></span>](developing-a-provider-with-the-osc-xml-schema.md)  
- [<span data-ttu-id="db1c2-138">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="db1c2-138">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

