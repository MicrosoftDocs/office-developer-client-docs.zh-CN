---
title: 测试功能、身份验证和配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 69e1f5bc-354c-4c33-84a1-b1aa10d4b650
description: 本主题介绍用于获取功能，并配置帐户和验证社交网络的用户设置的方案的测试。
ms.openlocfilehash: ac294291e2226dbb73f822b2a641fe2bf67ce5eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779333"
---
# <a name="testing-capabilities-authentication-and-configuration"></a><span data-ttu-id="48207-103">测试功能、身份验证和配置</span><span class="sxs-lookup"><span data-stu-id="48207-103">Testing capabilities, authentication, and configuration</span></span>

<span data-ttu-id="48207-104">本主题介绍用于获取功能，并配置帐户和验证社交网络的用户设置的方案的测试。</span><span class="sxs-lookup"><span data-stu-id="48207-104">This topic describes tests for getting capabilities, and scenarios around configuring an account and authenticating a user for a social network.</span></span>
  
## <a name="getting-capabilities"></a><span data-ttu-id="48207-105">获取功能</span><span class="sxs-lookup"><span data-stu-id="48207-105">Getting capabilities</span></span>

<span data-ttu-id="48207-106">Outlook Social Connector (OSC) 提供程序实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)和 OSC 呼叫**GetCapabilities**以获取提供程序支持的功能。</span><span class="sxs-lookup"><span data-stu-id="48207-106">A Outlook Social Connector (OSC) provider implements [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md), and the OSC calls **GetCapabilities** to get the functionality supported by the provider.</span></span> <span data-ttu-id="48207-107">为您的社交网络提供程序支持的功能应已知在实现，并且不应取决到实时社交网络的呼叫。</span><span class="sxs-lookup"><span data-stu-id="48207-107">The capabilities that your provider supports for your social network should be known at the point of implementation, and should not depend on a call to the social network in real time.</span></span> <span data-ttu-id="48207-108">例如，Outlook 用户可以脱机，启动 Outlook 并**GetCapabilities**无法在 Outlook 启动时依赖网络连接。</span><span class="sxs-lookup"><span data-stu-id="48207-108">For example, Outlook users can start Outlook offline, and **GetCapabilities** cannot rely on network connectivity at the time when Outlook starts.</span></span> 
  
<span data-ttu-id="48207-109">当测试提供程序，您应验证**GetCapabilities**返回_结果_字符串参数符合**capabilities**元素由 OSC 提供程序的 XML 架构定义。</span><span class="sxs-lookup"><span data-stu-id="48207-109">When testing the provider, you should verify that the  _results_ string parameter returned by **GetCapabilities** conforms to the **capabilities** element as defined by the OSC provider XML schema.</span></span> <span data-ttu-id="48207-110">有关详细信息，请参阅[功能 XML 元素](capabilities-xml-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="48207-110">For more information, see [Capabilities XML Elements](capabilities-xml-elements.md).</span></span>
  
## <a name="configuring-an-account"></a><span data-ttu-id="48207-111">配置帐户</span><span class="sxs-lookup"><span data-stu-id="48207-111">Configuring an account</span></span>

<span data-ttu-id="48207-112">当 OSC 配置帐户时，您应验证是否显示社交网络图标和名称，以及创建帐户和忘记了密码超链接显示在帐户配置对话框指定由提供商。</span><span class="sxs-lookup"><span data-stu-id="48207-112">When the OSC configures an account, you should verify whether the social network icon and name are displayed, and that the create-account and forgot-password hyperlinks appear in the account configuration dialog box as specified by the provider.</span></span>
  
### <a name="social-network-icon-and-name"></a><span data-ttu-id="48207-113">社交网络图标和名称</span><span class="sxs-lookup"><span data-stu-id="48207-113">Social network icon and name</span></span>

<span data-ttu-id="48207-114">获取功能之后, OSC 可以继续通过调用[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md)和[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md)获取的图标和社交网络的名称。</span><span class="sxs-lookup"><span data-stu-id="48207-114">After getting capabilities, the OSC can proceed to get the icon and name for the social network by calling [ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md) and [ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md).</span></span> <span data-ttu-id="48207-115">执行以下测试验证这些方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="48207-115">Do the following tests to verify that these method calls succeed.</span></span>
  
|<span data-ttu-id="48207-116">**要测试项**</span><span class="sxs-lookup"><span data-stu-id="48207-116">**Item to test**</span></span>|<span data-ttu-id="48207-117">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="48207-117">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48207-118">社交网络图标</span><span class="sxs-lookup"><span data-stu-id="48207-118">Social network icon</span></span>  <br/> | <span data-ttu-id="48207-119">在以下位置中 OSC 正确显示社交网络图标：</span><span class="sxs-lookup"><span data-stu-id="48207-119">The social network icon is displayed correctly in the following places in the OSC:</span></span>  <br/>  <span data-ttu-id="48207-120">在 OSC 对话框的**社交网络**帐户。</span><span class="sxs-lookup"><span data-stu-id="48207-120">In the OSC dialog box for **Social Network Accounts**.</span></span>  <br/>  <span data-ttu-id="48207-121">在下拉列表菜单当您尝试将某人添加为朋友。</span><span class="sxs-lookup"><span data-stu-id="48207-121">In the drop-down menu when you attempt to add a person as a friend.</span></span>  <br/>  <span data-ttu-id="48207-122">在以下朋友时标记。</span><span class="sxs-lookup"><span data-stu-id="48207-122">In the badge when following a friend.</span></span>  <br/> <br/><span data-ttu-id="48207-123">**注意**： 可以通过单击**视图**选项卡在 Outlook 中，在**人员窗格**组，单击**人员窗格**中，然后单击**帐户设置**的**社交网络帐户**访问对话框。</span><span class="sxs-lookup"><span data-stu-id="48207-123">**NOTE**:  You can access the dialog box for **Social Network Accounts** by clicking the **View** tab in Outlook, in the **People Pane** group, clicking **People Pane**, and then clicking **Account Settings**.</span></span>           |
|<span data-ttu-id="48207-124">社交网络名称</span><span class="sxs-lookup"><span data-stu-id="48207-124">Social network name</span></span>  <br/> | <span data-ttu-id="48207-125">在以下位置中 OSC 正确显示社交网络名称：</span><span class="sxs-lookup"><span data-stu-id="48207-125">The social network name is displayed correctly in the following places in the OSC:</span></span>  <br/>  <span data-ttu-id="48207-126">在 OSC 对话框的**社交网络**帐户。</span><span class="sxs-lookup"><span data-stu-id="48207-126">In the OSC dialog box for **Social Network Accounts**.</span></span>  <br/>  <span data-ttu-id="48207-127">在下拉列表菜单当您尝试将某人添加为朋友。</span><span class="sxs-lookup"><span data-stu-id="48207-127">In the drop-down menu when you attempt to add a person as a friend.</span></span>  <br/>  <span data-ttu-id="48207-128">为密码对话框中，当您尝试更改现有密码时的标题。</span><span class="sxs-lookup"><span data-stu-id="48207-128">As the title of the password dialog box when you attempt to change the existing password.</span></span>  <br/> |
   
### <a name="showing-hyperlinks-in-configuration-dialog"></a><span data-ttu-id="48207-129">在配置对话框中显示的超链接</span><span class="sxs-lookup"><span data-stu-id="48207-129">Showing hyperlinks in configuration dialog</span></span>

<span data-ttu-id="48207-130">调用**ISocialProvider::GetCapabilities**后, OSC 使用_结果_参数中**hideHyperlinks**元素的值来确定是否可隐藏或显示的**单击此处以创建帐户**和**忘记了您密码？** 在帐户配置对话框的超链接。</span><span class="sxs-lookup"><span data-stu-id="48207-130">After calling **ISocialProvider::GetCapabilities**, the OSC uses the value of the **hideHyperlinks** element in the  _results_ parameter to determine whether to hide or display the **Click here to create an account** and **Forgot your password?** hyperlinks in the account configuration dialog box.</span></span> <span data-ttu-id="48207-131">确认**hideHyperlinks**为**false**，是否帐户配置显示这些 Url。</span><span class="sxs-lookup"><span data-stu-id="48207-131">Verify that if **hideHyperlinks** is **false**, the account configuration displays these URLs.</span></span>
  
### <a name="support-to-create-account"></a><span data-ttu-id="48207-132">支持创建帐户</span><span class="sxs-lookup"><span data-stu-id="48207-132">Support to create account</span></span>

<span data-ttu-id="48207-133">如果从**ISocialProvider::GetCapabilities**方法调用_结果_参数设置为**false** **hideHyperlinks**元素和**createAccountUrl**元素设置为**true**，单击的 URL，验证默认 web 浏览器中打开页面。</span><span class="sxs-lookup"><span data-stu-id="48207-133">Verify that if the  _results_ parameter from the **ISocialProvider::GetCapabilities** method call has the **hideHyperlinks** element set to **false** and the **createAccountUrl** element set to **true**, clicking the URL opens the page in the default web browser.</span></span>
  
### <a name="support-for-forgotten-password"></a><span data-ttu-id="48207-134">忘记密码支持</span><span class="sxs-lookup"><span data-stu-id="48207-134">Support for forgotten password</span></span>

<span data-ttu-id="48207-135">如果从**ISocialProvider::GetCapabilities**方法调用_结果_参数设置为**false** **hideHyperlinks**元素和**forgotPasswordUrl**元素设置为**true**，单击的 URL，验证默认 web 浏览器中打开页面。</span><span class="sxs-lookup"><span data-stu-id="48207-135">Verify that if the  _results_ parameter from the **ISocialProvider::GetCapabilities** method call has the **hideHyperlinks** element set to **false** and the **forgotPasswordUrl** element set to **true**, clicking the URL opens the page in the default web browser.</span></span>
  
## <a name="authenticating-users"></a><span data-ttu-id="48207-136">对用户进行身份验证</span><span class="sxs-lookup"><span data-stu-id="48207-136">Authenticating users</span></span>

<span data-ttu-id="48207-137">测试在以下情况下，无论您 OSC 提供程序是否支持基本身份验证或基于表单的身份验证。</span><span class="sxs-lookup"><span data-stu-id="48207-137">Test for the following scenarios regardless of whether your OSC provider supports basic authentication or forms-based authentication.</span></span>
  
|<span data-ttu-id="48207-138">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="48207-138">**Scenario**</span></span>|<span data-ttu-id="48207-139">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="48207-139">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48207-140">首次登录。</span><span class="sxs-lookup"><span data-stu-id="48207-140">Logging on for the first time.</span></span>  <br/> |<span data-ttu-id="48207-141">用户可以成功登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="48207-141">The user can successfully log on to the social network.</span></span>  <br/> |
|<span data-ttu-id="48207-142">使用不同的字符，包括标点和 Unicode 字符组成的密码进行登录。</span><span class="sxs-lookup"><span data-stu-id="48207-142">Logging on with a password made up of a variety of characters, including punctuation and Unicode characters.</span></span>  <br/> |<span data-ttu-id="48207-143">用户可以成功登录到社交网络时，在密码中使用的字符类型的独立。</span><span class="sxs-lookup"><span data-stu-id="48207-143">The user can successfully log on to the social network, independent of the kind of characters used in the password.</span></span>  <br/> |
|<span data-ttu-id="48207-144">对话框中的**社交网络帐户**显示用户名称或 id。</span><span class="sxs-lookup"><span data-stu-id="48207-144">The dialog box for **Social Network Accounts** displaying the user name or ID.</span></span>  <br/> |<span data-ttu-id="48207-145">用户具有成功登录到网络后，对于**社交网络帐户**的 OSC 的对话框中显示登录用户的名称或 id。</span><span class="sxs-lookup"><span data-stu-id="48207-145">After the user has successfully logged on to the network, the OSC's dialog box for **Social Network Accounts** displays the logged-on user name or ID.</span></span>  <br/> |
|<span data-ttu-id="48207-146">身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="48207-146">Authentication fails.</span></span>  <br/> |<span data-ttu-id="48207-147">OSC 显示错误**无效的用户名或密码**。</span><span class="sxs-lookup"><span data-stu-id="48207-147">The OSC displays the error **Invalid user name or password**.</span></span>  <br/> |
|<span data-ttu-id="48207-148">无法连接到社交网络。</span><span class="sxs-lookup"><span data-stu-id="48207-148">Cannot connect to the social network.</span></span>  <br/> |<span data-ttu-id="48207-149">OSC 显示**找不到服务器**的错误。</span><span class="sxs-lookup"><span data-stu-id="48207-149">The OSC displays the error **Server cannot be found**.</span></span>  <br/> |
|<span data-ttu-id="48207-150">能够检索项目。</span><span class="sxs-lookup"><span data-stu-id="48207-150">Being able to retrieve items.</span></span>  <br/> |<span data-ttu-id="48207-151">当用户具有身份验证时，应允许所有活动。</span><span class="sxs-lookup"><span data-stu-id="48207-151">Once the user has authenticated, all activity should be allowed.</span></span> <span data-ttu-id="48207-152">没有任何错误，获取朋友的数据或活动。</span><span class="sxs-lookup"><span data-stu-id="48207-152">There are no errors getting friends' data or activities.</span></span>  <br/> |
|<span data-ttu-id="48207-153">登录后重新启动 Outlook 社交网络。</span><span class="sxs-lookup"><span data-stu-id="48207-153">Logging on to the social network after restarting Outlook.</span></span>  <br/> |<span data-ttu-id="48207-154">如果 OSC 提供程序允许缓存的密码，用户已通过身份验证的第一次后，不随后提示用户凭据时 OSC 尝试从社交网络中获取数据。</span><span class="sxs-lookup"><span data-stu-id="48207-154">If the OSC provider allows caching of the password, after the user has authenticated the first time, the user is not subsequently prompted for credentials whenever the OSC attempts to get data from the social network.</span></span>  <br/> |
   
<span data-ttu-id="48207-155">此外，如果您 OSC 提供程序支持基于表单的身份验证，测试以下方案。</span><span class="sxs-lookup"><span data-stu-id="48207-155">In addition, if your OSC provider supports forms-based authentication, test for the following scenario as well.</span></span>
  
|<span data-ttu-id="48207-156">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="48207-156">**Scenario**</span></span>|<span data-ttu-id="48207-157">**预期的行为**</span><span class="sxs-lookup"><span data-stu-id="48207-157">**Expected behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48207-158">获取向用户窗体 URL 以从调用[ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md)登录 OSC。</span><span class="sxs-lookup"><span data-stu-id="48207-158">The OSC getting a URL to a form for the user to log on from calling [ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md).</span></span>  <br/> |<span data-ttu-id="48207-159">OSC 打开 URL 以在用户的默认浏览器，并在网页允许用户输入凭据登录到社交网络。</span><span class="sxs-lookup"><span data-stu-id="48207-159">The OSC opens the URL in the user's default browser, and the webpage allows the user to enter credentials to log on to the social network.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="48207-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48207-160">See also</span></span>

- [<span data-ttu-id="48207-161">功能 XML 元素</span><span class="sxs-lookup"><span data-stu-id="48207-161">Capabilities XML Elements</span></span>](capabilities-xml-elements.md)  
- [<span data-ttu-id="48207-162">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="48207-162">Basic Authentication</span></span>](basic-authentication.md) 
- [<span data-ttu-id="48207-163">基于表单的身份验证</span><span class="sxs-lookup"><span data-stu-id="48207-163">Forms-Based Authentication</span></span>](forms-based-authentication.md)
- [<span data-ttu-id="48207-164">准备发布 OSC 提供程序</span><span class="sxs-lookup"><span data-stu-id="48207-164">Getting Ready to Release an OSC Provider</span></span>](getting-ready-to-release-an-osc-provider.md)

