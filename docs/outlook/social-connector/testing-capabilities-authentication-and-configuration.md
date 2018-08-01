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
# <a name="testing-capabilities-authentication-and-configuration"></a>测试功能、身份验证和配置

本主题介绍用于获取功能，并配置帐户和验证社交网络的用户设置的方案的测试。
  
## <a name="getting-capabilities"></a>获取功能

Outlook Social Connector (OSC) 提供程序实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)和 OSC 呼叫**GetCapabilities**以获取提供程序支持的功能。 为您的社交网络提供程序支持的功能应已知在实现，并且不应取决到实时社交网络的呼叫。 例如，Outlook 用户可以脱机，启动 Outlook 并**GetCapabilities**无法在 Outlook 启动时依赖网络连接。 
  
当测试提供程序，您应验证**GetCapabilities**返回_结果_字符串参数符合**capabilities**元素由 OSC 提供程序的 XML 架构定义。 有关详细信息，请参阅[功能 XML 元素](capabilities-xml-elements.md)。
  
## <a name="configuring-an-account"></a>配置帐户

当 OSC 配置帐户时，您应验证是否显示社交网络图标和名称，以及创建帐户和忘记了密码超链接显示在帐户配置对话框指定由提供商。
  
### <a name="social-network-icon-and-name"></a>社交网络图标和名称

获取功能之后, OSC 可以继续通过调用[ISocialProvider::SocialNetworkIcon](isocialprovider-socialnetworkicon.md)和[ISocialProvider::SocialNetworkName](isocialprovider-socialnetworkname.md)获取的图标和社交网络的名称。 执行以下测试验证这些方法调用成功。
  
|**要测试项**|**预期的行为**|
|:-----|:-----|
|社交网络图标  <br/> | 在以下位置中 OSC 正确显示社交网络图标：  <br/>  在 OSC 对话框的**社交网络**帐户。  <br/>  在下拉列表菜单当您尝试将某人添加为朋友。  <br/>  在以下朋友时标记。  <br/> <br/>**注意**： 可以通过单击**视图**选项卡在 Outlook 中，在**人员窗格**组，单击**人员窗格**中，然后单击**帐户设置**的**社交网络帐户**访问对话框。           |
|社交网络名称  <br/> | 在以下位置中 OSC 正确显示社交网络名称：  <br/>  在 OSC 对话框的**社交网络**帐户。  <br/>  在下拉列表菜单当您尝试将某人添加为朋友。  <br/>  为密码对话框中，当您尝试更改现有密码时的标题。  <br/> |
   
### <a name="showing-hyperlinks-in-configuration-dialog"></a>在配置对话框中显示的超链接

调用**ISocialProvider::GetCapabilities**后, OSC 使用_结果_参数中**hideHyperlinks**元素的值来确定是否可隐藏或显示的**单击此处以创建帐户**和**忘记了您密码？** 在帐户配置对话框的超链接。 确认**hideHyperlinks**为**false**，是否帐户配置显示这些 Url。
  
### <a name="support-to-create-account"></a>支持创建帐户

如果从**ISocialProvider::GetCapabilities**方法调用_结果_参数设置为**false** **hideHyperlinks**元素和**createAccountUrl**元素设置为**true**，单击的 URL，验证默认 web 浏览器中打开页面。
  
### <a name="support-for-forgotten-password"></a>忘记密码支持

如果从**ISocialProvider::GetCapabilities**方法调用_结果_参数设置为**false** **hideHyperlinks**元素和**forgotPasswordUrl**元素设置为**true**，单击的 URL，验证默认 web 浏览器中打开页面。
  
## <a name="authenticating-users"></a>对用户进行身份验证

测试在以下情况下，无论您 OSC 提供程序是否支持基本身份验证或基于表单的身份验证。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|首次登录。  <br/> |用户可以成功登录到社交网络。  <br/> |
|使用不同的字符，包括标点和 Unicode 字符组成的密码进行登录。  <br/> |用户可以成功登录到社交网络时，在密码中使用的字符类型的独立。  <br/> |
|对话框中的**社交网络帐户**显示用户名称或 id。  <br/> |用户具有成功登录到网络后，对于**社交网络帐户**的 OSC 的对话框中显示登录用户的名称或 id。  <br/> |
|身份验证失败。  <br/> |OSC 显示错误**无效的用户名或密码**。  <br/> |
|无法连接到社交网络。  <br/> |OSC 显示**找不到服务器**的错误。  <br/> |
|能够检索项目。  <br/> |当用户具有身份验证时，应允许所有活动。 没有任何错误，获取朋友的数据或活动。  <br/> |
|登录后重新启动 Outlook 社交网络。  <br/> |如果 OSC 提供程序允许缓存的密码，用户已通过身份验证的第一次后，不随后提示用户凭据时 OSC 尝试从社交网络中获取数据。  <br/> |
   
此外，如果您 OSC 提供程序支持基于表单的身份验证，测试以下方案。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|获取向用户窗体 URL 以从调用[ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md)登录 OSC。  <br/> |OSC 打开 URL 以在用户的默认浏览器，并在网页允许用户输入凭据登录到社交网络。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [功能 XML 元素](capabilities-xml-elements.md)  
- [基本身份验证](basic-authentication.md) 
- [基于表单的身份验证](forms-based-authentication.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

