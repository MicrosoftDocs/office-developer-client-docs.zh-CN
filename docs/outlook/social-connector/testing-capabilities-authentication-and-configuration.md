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
# <a name="testing-capabilities-authentication-and-configuration"></a>测试功能、身份验证和配置

本主题介绍用于获取功能的测试，以及有关为社交网络配置帐户和验证用户的方案。
  
## <a name="getting-capabilities"></a>获取功能

Outlook Social Connector (OSC) 提供程序实现 [ISocialProvider：：GetCapabilities，](isocialprovider-getcapabilities.md)而 OSC 调用 **GetCapabilities** 获取提供程序支持的功能。 您的提供商为社交网络支持的功能应在实现时已知，并且不应依赖于实时调用社交网络。 例如，Outlook可以脱机Outlook，**并且 GetCapabilities** 在启动时不能依赖网络连接Outlook连接。 
  
测试提供程序时，应验证 **GetCapabilities** 返回的结果字符串参数是否符合 OSC 提供程序 XML 架构定义的 **capabilities** 元素。  有关详细信息，请参阅[Capabilities XML Elements。](capabilities-xml-elements.md)
  
## <a name="configuring-an-account"></a>配置帐户

当 OSC 配置帐户时，应验证是否显示社交网络图标和名称，以及创建帐户和忘记密码超链接是否显示在提供程序指定的帐户配置对话框中。
  
### <a name="social-network-icon-and-name"></a>社交网络图标和名称

获取功能后，OSC 可以继续通过调用 [ISocialProvider：：SocialNetworkIcon](isocialprovider-socialnetworkicon.md) 和 [ISocialProvider：：SocialNetworkName](isocialprovider-socialnetworkname.md)获取社交网络的图标和名称。 执行以下测试以验证这些方法调用是否成功。
  
|**要测试的项目**|**预期行为**|
|:-----|:-----|
|社交网络图标  <br/> | 社交网络图标在 OSC 中的以下位置正确显示：  <br/>  在社交网络帐户 的 OSC **对话框中**。  <br/>  当您尝试将某人添加为好友时，在下拉菜单中。  <br/>  在锁屏提醒中，当跟踪好友时。  <br/> <br/>**注意**：可以通过以下操作访问 **"** 社交网络帐户"对话框：单击 Outlook中的"视图"选项卡，在"人员窗格"组中单击"人员窗格 **"，** 然后单击"帐户"设置。           |
|社交网络名称  <br/> | 社交网络名称在 OSC 中的以下位置正确显示：  <br/>  在社交网络帐户 的 OSC **对话框中**。  <br/>  当您尝试将某人添加为好友时，在下拉菜单中。  <br/>  作为尝试更改现有密码时的密码对话框的标题。  <br/> |
   
### <a name="showing-hyperlinks-in-configuration-dialog"></a>在配置对话框中显示超链接

调用 **ISocialProvider：：GetCapabilities** 后，OSC 使用 _results_ 参数中 **hideHyperlinks** 元素的值来确定是隐藏还是显示"单击此处创建帐户"和"忘记密码？"超链接，在帐户配置对话框中显示超链接。 验证如果 **hideHyperlinks** 为 **false，** 则帐户配置显示这些 URL。
  
### <a name="support-to-create-account"></a>支持创建帐户

验证 **ISocialProvider：：GetCapabilities** 方法调用的结果参数是否将 **hideHyperlinks** 元素设置为 **false，** 将 **createAccountUrl** 元素设置为 **true，** 单击 URL 将在默认 Web 浏览器中打开页面。 
  
### <a name="support-for-forgotten-password"></a>支持忘记密码

验证如果 **ISocialProvider：：GetCapabilities** 方法调用的 _results_ 参数将 **hideHyperlinks** 元素设置为 **false，** 并且 **将 forgotPasswordUrl** 元素设置为 **true，** 则单击 URL 将在默认 Web 浏览器中打开页面。
  
## <a name="authenticating-users"></a>对用户进行身份验证

无论 OSC 提供程序支持基本身份验证还是基于表单的身份验证，都测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|首次登录。  <br/> |用户可以成功登录到社交网络。  <br/> |
|使用由各种字符（包括标点符号和 Unicode 字符）组成的密码登录。  <br/> |用户可以成功登录到社交网络，而与密码中使用的字符类型无关。  <br/> |
|显示用户名或 ID 的 **"社交网络** 帐户"对话框。  <br/> |在用户成功登录到网络后，"社交网络帐户"的 OSC 对话框将显示登录的用户名或 ID。  <br/> |
|身份验证失败。  <br/> |OSC 显示错误"**用户名或密码无效"。**  <br/> |
|无法连接到社交网络。  <br/> |OSC 显示找不到 **错误"服务器"。**  <br/> |
|能够检索项目。  <br/> |对用户进行身份验证后，应允许所有活动。 获取好友的数据或活动没有错误。  <br/> |
|重启后登录到社交网络Outlook。  <br/> |如果 OSC 提供程序允许缓存密码，则用户首次进行身份验证后，只要 OSC 尝试从社交网络获取数据，系统随后不会提示用户输入凭据。  <br/> |
   
此外，如果您的 OSC 提供程序支持基于表单的身份验证，请测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|OSC 获取表单 URL，用户通过调用 [ISocialSession：：GetLogonUrl 登录](isocialsession-getlogonurl.md)。  <br/> |OSC 在用户的默认浏览器中打开 URL，网页允许用户输入凭据以登录到社交网络。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [功能 XML 元素](capabilities-xml-elements.md)  
- [基本身份验证](basic-authentication.md) 
- [基于表单的身份验证](forms-based-authentication.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

