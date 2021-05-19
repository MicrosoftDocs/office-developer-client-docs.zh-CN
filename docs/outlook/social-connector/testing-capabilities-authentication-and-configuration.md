---
title: 测试功能、身份验证和配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 69e1f5bc-354c-4c33-84a1-b1aa10d4b650
description: 本主题介绍用于获取功能的测试，以及有关为社交网络配置帐户和验证用户的方案。
ms.openlocfilehash: 218d5c564dd18e1e72820e31079011e6bb81a33c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423501"
---
# <a name="testing-capabilities-authentication-and-configuration"></a><span data-ttu-id="8b13a-103">测试功能、身份验证和配置</span><span class="sxs-lookup"><span data-stu-id="8b13a-103">Testing capabilities, authentication, and configuration</span></span>

<span data-ttu-id="8b13a-104">本主题介绍用于获取功能的测试，以及有关为社交网络配置帐户和验证用户的方案。</span><span class="sxs-lookup"><span data-stu-id="8b13a-104">This topic describes tests for getting capabilities, and scenarios around configuring an account and authenticating a user for a social network.</span></span>
  
## <a name="getting-capabilities"></a><span data-ttu-id="8b13a-105">获取功能</span><span class="sxs-lookup"><span data-stu-id="8b13a-105">Getting capabilities</span></span>

<span data-ttu-id="8b13a-106">Outlook Social Connector (OSC) 提供程序实现 [ISocialProvider：：GetCapabilities，](isocialprovider-getcapabilities.md)而 OSC 调用 **GetCapabilities** 获取提供程序支持的功能。</span><span class="sxs-lookup"><span data-stu-id="8b13a-106">A Outlook Social Connector (OSC) provider implements [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md), and the OSC calls **GetCapabilities** to get the functionality supported by the provider.</span></span> <span data-ttu-id="8b13a-107">您的提供商为社交网络支持的功能应在实现时已知，并且不应依赖于实时调用社交网络。</span><span class="sxs-lookup"><span data-stu-id="8b13a-107">The capabilities that your provider supports for your social network should be known at the point of implementation, and should not depend on a call to the social network in real time.</span></span> <span data-ttu-id="8b13a-108">例如，Outlook可以脱机Outlook，**并且 GetCapabilities** 在启动时不能依赖网络连接Outlook连接。</span><span class="sxs-lookup"><span data-stu-id="8b13a-108">For example, Outlook users can start Outlook offline, and **GetCapabilities** cannot rely on network connectivity at the time when Outlook starts.</span></span> 
  
<span data-ttu-id="8b13a-109">测试提供程序时，应验证 **GetCapabilities** 返回的结果字符串参数是否符合 OSC 提供程序 XML 架构定义的 **capabilities** 元素。 </span><span class="sxs-lookup"><span data-stu-id="8b13a-109">When testing the provider, you should verify that the  _results_ string parameter returned by **GetCapabilities** conforms to the **capabilities** element as defined by the OSC provider XML schema.</span></span> <span data-ttu-id="8b13a-110">有关详细信息，请参阅[Capabilities XML Elements。](capabilities-xml-elements.md)</span><span class="sxs-lookup"><span data-stu-id="8b13a-110">For more information, see [Capabilities XML Elements](capabilities-xml-elements.md).</span></span>
  
## <a name="configuring-an-account"></a><span data-ttu-id="8b13a-111">配置帐户</span><span class="sxs-lookup"><span data-stu-id="8b13a-111">Configuring an account</span></span>

<span data-ttu-id="8b13a-112">当 OSC 配置帐户时，应验证是否显示社交网络图标和名称，以及创建帐户和忘记密码超链接是否显示在提供程序指定的帐户配置对话框中。</span><span class="sxs-lookup"><span data-stu-id="8b13a-112">When the OSC configures an account, you should verify whether the social network icon and name are displayed, and that the create-account and forgot-password hyperlinks appear in the account configuration dialog box as specified by the provider.</span></span>
  
### <a name="social-network-icon-and-name"></a><span data-ttu-id="8b13a-113">社交网络图标和名称</span><span class="sxs-lookup"><span data-stu-id="8b13a-113">Social network icon and name</span></span>

<span data-ttu-id="8b13a-114">获取功能后，OSC 可以继续通过调用 [ISocialProvider：：SocialNetworkIcon](isocialprovider-socialnetworkicon.md) 和 [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md)获取社交网络的图标和名称。</span><span class="sxs-lookup"><span data-stu-id="8b13a-114">After getting capabilities, the OSC can proceed to get the icon and name for the social network by calling [ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) and [ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md).</span></span> <span data-ttu-id="8b13a-115">执行以下测试以验证这些方法调用是否成功。</span><span class="sxs-lookup"><span data-stu-id="8b13a-115">Do the following tests to verify that these method calls succeed.</span></span>
  
|<span data-ttu-id="8b13a-116">**要测试的项目**</span><span class="sxs-lookup"><span data-stu-id="8b13a-116">**Item to test**</span></span>|<span data-ttu-id="8b13a-117">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="8b13a-117">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b13a-118">社交网络图标</span><span class="sxs-lookup"><span data-stu-id="8b13a-118">Social network icon</span></span>  <br/> | <span data-ttu-id="8b13a-119">社交网络图标在 OSC 中的以下位置正确显示：</span><span class="sxs-lookup"><span data-stu-id="8b13a-119">The social network icon is displayed correctly in the following places in the OSC:</span></span>  <br/>  <span data-ttu-id="8b13a-120">在社交网络帐户 的 OSC **对话框中**。</span><span class="sxs-lookup"><span data-stu-id="8b13a-120">In the OSC dialog box for **Social Network Accounts**.</span></span>  <br/>  <span data-ttu-id="8b13a-121">当您尝试将某人添加为好友时，在下拉菜单中。</span><span class="sxs-lookup"><span data-stu-id="8b13a-121">In the drop-down menu when you attempt to add a person as a friend.</span></span>  <br/>  <span data-ttu-id="8b13a-122">在锁屏提醒中，当跟踪好友时。</span><span class="sxs-lookup"><span data-stu-id="8b13a-122">In the badge when following a friend.</span></span>  <br/> <br/><span data-ttu-id="8b13a-123">**注意**：可以通过以下操作访问 **"** 社交网络帐户"对话框：单击 Outlook中的"视图"选项卡，在"人员窗格"组中单击"人员窗格 **"，** 然后单击"帐户"设置。</span><span class="sxs-lookup"><span data-stu-id="8b13a-123">**NOTE**:  You can access the dialog box for **Social Network Accounts** by clicking the **View** tab in Outlook, in the **People Pane** group, clicking **People Pane**, and then clicking **Account Settings**.</span></span>           |
|<span data-ttu-id="8b13a-124">社交网络名称</span><span class="sxs-lookup"><span data-stu-id="8b13a-124">Social network name</span></span>  <br/> | <span data-ttu-id="8b13a-125">社交网络名称在 OSC 中的以下位置正确显示：</span><span class="sxs-lookup"><span data-stu-id="8b13a-125">The social network name is displayed correctly in the following places in the OSC:</span></span>  <br/>  <span data-ttu-id="8b13a-126">在社交网络帐户 的 OSC **对话框中**。</span><span class="sxs-lookup"><span data-stu-id="8b13a-126">In the OSC dialog box for **Social Network Accounts**.</span></span>  <br/>  <span data-ttu-id="8b13a-127">当您尝试将某人添加为好友时，在下拉菜单中。</span><span class="sxs-lookup"><span data-stu-id="8b13a-127">In the drop-down menu when you attempt to add a person as a friend.</span></span>  <br/>  <span data-ttu-id="8b13a-128">作为尝试更改现有密码时的密码对话框的标题。</span><span class="sxs-lookup"><span data-stu-id="8b13a-128">As the title of the password dialog box when you attempt to change the existing password.</span></span>  <br/> |
   
### <a name="showing-hyperlinks-in-configuration-dialog"></a><span data-ttu-id="8b13a-129">在配置对话框中显示超链接</span><span class="sxs-lookup"><span data-stu-id="8b13a-129">Showing hyperlinks in configuration dialog</span></span>

<span data-ttu-id="8b13a-130">调用 **ISocialProvider：：GetCapabilities** 后，OSC 使用 _results_ 参数中 **hideHyperlinks** 元素的值来确定是隐藏还是显示"单击此处创建帐户"和"忘记密码？"超链接，在帐户配置对话框中显示超链接。</span><span class="sxs-lookup"><span data-stu-id="8b13a-130">After calling **ISocialProvider::GetCapabilities**, the OSC uses the value of the **hideHyperlinks** element in the  _results_ parameter to determine whether to hide or display the **Click here to create an account** and **Forgot your password?** hyperlinks in the account configuration dialog box.</span></span> <span data-ttu-id="8b13a-131">验证如果 **hideHyperlinks** 为 **false，** 则帐户配置显示这些 URL。</span><span class="sxs-lookup"><span data-stu-id="8b13a-131">Verify that if **hideHyperlinks** is **false**, the account configuration displays these URLs.</span></span>
  
### <a name="support-to-create-account"></a><span data-ttu-id="8b13a-132">支持创建帐户</span><span class="sxs-lookup"><span data-stu-id="8b13a-132">Support to create account</span></span>

<span data-ttu-id="8b13a-133">验证 **ISocialProvider：：GetCapabilities** 方法调用的结果参数是否将 **hideHyperlinks** 元素设置为 **false，** 将 **createAccountUrl** 元素设置为 **true，** 单击 URL 将在默认 Web 浏览器中打开页面。 </span><span class="sxs-lookup"><span data-stu-id="8b13a-133">Verify that if the  _results_ parameter from the **ISocialProvider::GetCapabilities** method call has the **hideHyperlinks** element set to **false** and the **createAccountUrl** element set to **true**, clicking the URL opens the page in the default web browser.</span></span>
  
### <a name="support-for-forgotten-password"></a><span data-ttu-id="8b13a-134">支持忘记密码</span><span class="sxs-lookup"><span data-stu-id="8b13a-134">Support for forgotten password</span></span>

<span data-ttu-id="8b13a-135">验证如果 **ISocialProvider：：GetCapabilities** 方法调用的 _results_ 参数将 **hideHyperlinks** 元素设置为 **false，** 并且 **将 forgotPasswordUrl** 元素设置为 **true，** 则单击 URL 将在默认 Web 浏览器中打开页面。</span><span class="sxs-lookup"><span data-stu-id="8b13a-135">Verify that if the  _results_ parameter from the **ISocialProvider::GetCapabilities** method call has the **hideHyperlinks** element set to **false** and the **forgotPasswordUrl** element set to **true**, clicking the URL opens the page in the default web browser.</span></span>
  
## <a name="authenticating-users"></a><span data-ttu-id="8b13a-136">对用户进行身份验证</span><span class="sxs-lookup"><span data-stu-id="8b13a-136">Authenticating users</span></span>

<span data-ttu-id="8b13a-137">无论 OSC 提供程序支持基本身份验证还是基于表单的身份验证，都测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="8b13a-137">Test for the following scenarios regardless of whether your OSC provider supports basic authentication or forms-based authentication.</span></span>
  
|<span data-ttu-id="8b13a-138">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="8b13a-138">**Scenario**</span></span>|<span data-ttu-id="8b13a-139">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="8b13a-139">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b13a-140">首次登录。</span><span class="sxs-lookup"><span data-stu-id="8b13a-140">Logging on for the first time.</span></span>  <br/> |<span data-ttu-id="8b13a-141">用户可以成功登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="8b13a-141">The user can successfully log on to the social network.</span></span>  <br/> |
|<span data-ttu-id="8b13a-142">使用由各种字符（包括标点符号和 Unicode 字符）组成的密码登录。</span><span class="sxs-lookup"><span data-stu-id="8b13a-142">Logging on with a password made up of a variety of characters, including punctuation and Unicode characters.</span></span>  <br/> |<span data-ttu-id="8b13a-143">用户可以成功登录到社交网络，而与密码中使用的字符类型无关。</span><span class="sxs-lookup"><span data-stu-id="8b13a-143">The user can successfully log on to the social network, independent of the kind of characters used in the password.</span></span>  <br/> |
|<span data-ttu-id="8b13a-144">显示用户名或 ID 的 **"社交网络** 帐户"对话框。</span><span class="sxs-lookup"><span data-stu-id="8b13a-144">The dialog box for **Social Network Accounts** displaying the user name or ID.</span></span>  <br/> |<span data-ttu-id="8b13a-145">在用户成功登录到网络后，"社交网络帐户"的 OSC 对话框将显示登录的用户名或 ID。</span><span class="sxs-lookup"><span data-stu-id="8b13a-145">After the user has successfully logged on to the network, the OSC's dialog box for **Social Network Accounts** displays the logged-on user name or ID.</span></span>  <br/> |
|<span data-ttu-id="8b13a-146">身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="8b13a-146">Authentication fails.</span></span>  <br/> |<span data-ttu-id="8b13a-147">OSC 显示错误"**用户名或密码无效"。**</span><span class="sxs-lookup"><span data-stu-id="8b13a-147">The OSC displays the error **Invalid user name or password**.</span></span>  <br/> |
|<span data-ttu-id="8b13a-148">无法连接到社交网络。</span><span class="sxs-lookup"><span data-stu-id="8b13a-148">Cannot connect to the social network.</span></span>  <br/> |<span data-ttu-id="8b13a-149">OSC 显示找不到 **错误"服务器"。**</span><span class="sxs-lookup"><span data-stu-id="8b13a-149">The OSC displays the error **Server cannot be found**.</span></span>  <br/> |
|<span data-ttu-id="8b13a-150">能够检索项目。</span><span class="sxs-lookup"><span data-stu-id="8b13a-150">Being able to retrieve items.</span></span>  <br/> |<span data-ttu-id="8b13a-151">对用户进行身份验证后，应允许所有活动。</span><span class="sxs-lookup"><span data-stu-id="8b13a-151">Once the user has authenticated, all activity should be allowed.</span></span> <span data-ttu-id="8b13a-152">获取好友的数据或活动没有错误。</span><span class="sxs-lookup"><span data-stu-id="8b13a-152">There are no errors getting friends' data or activities.</span></span>  <br/> |
|<span data-ttu-id="8b13a-153">重启后登录到社交网络Outlook。</span><span class="sxs-lookup"><span data-stu-id="8b13a-153">Logging on to the social network after restarting Outlook.</span></span>  <br/> |<span data-ttu-id="8b13a-154">如果 OSC 提供程序允许缓存密码，则用户首次进行身份验证后，只要 OSC 尝试从社交网络获取数据，系统随后不会提示用户输入凭据。</span><span class="sxs-lookup"><span data-stu-id="8b13a-154">If the OSC provider allows caching of the password, after the user has authenticated the first time, the user is not subsequently prompted for credentials whenever the OSC attempts to get data from the social network.</span></span>  <br/> |
   
<span data-ttu-id="8b13a-155">此外，如果您的 OSC 提供程序支持基于表单的身份验证，请测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="8b13a-155">In addition, if your OSC provider supports forms-based authentication, test for the following scenario as well.</span></span>
  
|<span data-ttu-id="8b13a-156">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="8b13a-156">**Scenario**</span></span>|<span data-ttu-id="8b13a-157">**预期行为**</span><span class="sxs-lookup"><span data-stu-id="8b13a-157">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b13a-158">OSC 获取表单 URL，用户通过调用 [ISocialSession：：GetLogonUrl 登录](isocialsession-getlogonurl.md)。</span><span class="sxs-lookup"><span data-stu-id="8b13a-158">The OSC getting a URL to a form for the user to log on from calling [ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md).</span></span>  <br/> |<span data-ttu-id="8b13a-159">OSC 在用户的默认浏览器中打开 URL，网页允许用户输入凭据以登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="8b13a-159">The OSC opens the URL in the user's default browser, and the webpage allows the user to enter credentials to log on to the social network.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8b13a-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b13a-160">See also</span></span>

- [<span data-ttu-id="8b13a-161">功能 XML 元素</span><span class="sxs-lookup"><span data-stu-id="8b13a-161">Capabilities XML Elements</span></span>](capabilities-xml-elements.md)  
- [<span data-ttu-id="8b13a-162">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="8b13a-162">Basic Authentication</span></span>](basic-authentication.md) 
- [<span data-ttu-id="8b13a-163">基于表单的身份验证</span><span class="sxs-lookup"><span data-stu-id="8b13a-163">Forms-Based Authentication</span></span>](forms-based-authentication.md)
- [<span data-ttu-id="8b13a-164">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="8b13a-164">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

