---
title: 测试功能、身份验证和配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 69e1f5bc-354c-4c33-84a1-b1aa10d4b650
description: 本主题介绍了用于获取功能的测试, 以及有关配置帐户和对社交网络的用户进行身份验证的方案。
ms.openlocfilehash: 218d5c564dd18e1e72820e31079011e6bb81a33c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329167"
---
# <a name="testing-capabilities-authentication-and-configuration"></a>测试功能、身份验证和配置

本主题介绍了用于获取功能的测试, 以及有关配置帐户和对社交网络的用户进行身份验证的方案。
  
## <a name="getting-capabilities"></a>获取功能

Outlook Social Connector (.osc) 提供程序实现[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md), 并且 .osc 调用**GetCapabilities** , 以获取提供程序支持的功能。 您的您的社交网络的提供商支持的功能应在实施时知道, 并且不应实时依赖社交网络的呼叫。 例如, outlook 用户可以脱机启动 outlook, 并且**GetCapabilities**在 Outlook 启动时无法依赖网络连接。 
  
测试提供程序时, 应验证**GetCapabilities**返回的_结果_字符串参数是否符合 .osc 提供程序 XML 架构定义的**功能**元素。 有关详细信息, 请参阅[功能 XML 元素](capabilities-xml-elements.md)。
  
## <a name="configuring-an-account"></a>配置帐户

当 .osc 配置帐户时, 应验证是否显示了社交网络图标和名称, 以及是否在 "帐户配置" 对话框中显示由提供程序指定的 "创建帐户" 和 "忘记密码" 超链接。
  
### <a name="social-network-icon-and-name"></a>社交网络图标和名称

获取功能后, .osc 可以通过调用[ISocialProvider:: SocialNetworkIcon](isocialprovider-socialnetworkicon.md)和[ISocialProvider:: SocialNetworkName](isocialprovider-socialnetworkname.md)继续获取社交网络的图标和名称。 执行以下测试以验证这些方法调用是否成功。
  
|**要测试的项**|**预期行为**|
|:-----|:-----|
|社交网络图标  <br/> | 社交网络图标在 .osc 中的以下位置正确显示:  <br/>  在用于**社交网络帐户**的 .osc 对话框中。  <br/>  当您尝试将某个人添加为朋友时, 在下拉菜单中。  <br/>  在关注好友时的徽章中。  <br/> <br/>**注意**: 通过单击 Outlook 中的 "**视图**" 选项卡, 在 "**人员" 窗格**组中, 单击 "**人员窗格**", 然后单击 "**帐户设置**", 可以访问**社交网络帐户**的对话框。           |
|社交网络名称  <br/> | 社交网络名称在 .osc 中的以下位置正确显示:  <br/>  在用于**社交网络帐户**的 .osc 对话框中。  <br/>  当您尝试将某个人添加为朋友时, 在下拉菜单中。  <br/>  当您尝试更改现有密码时, 作为密码对话框的标题。  <br/> |
   
### <a name="showing-hyperlinks-in-configuration-dialog"></a>在配置对话框中显示超链接

在调用**ISocialProvider:: GetCapabilities**后, .osc 使用_results_参数中的**hideHyperlinks**元素的值来确定是隐藏还是显示 "**单击此处创建帐户**并**忘记密码？**"帐户配置" 对话框中的超链接。 确认如果**hideHyperlinks**为**false**, 帐户配置将显示这些 url。
  
### <a name="support-to-create-account"></a>支持创建帐户

确认如果**ISocialProvider:: GetCapabilities**方法调用的_results_参数的**hideHyperlinks**元素设置为**false** , 并且**createAccountUrl**元素设置为**true**, 则单击 URL在默认 web 浏览器中打开页面。
  
### <a name="support-for-forgotten-password"></a>对忘记的密码的支持

确认如果**ISocialProvider:: GetCapabilities**方法调用的_results_参数的**hideHyperlinks**元素设置为**false** , 并且**forgotPasswordUrl**元素设置为**true**, 则单击 URL在默认 web 浏览器中打开页面。
  
## <a name="authenticating-users"></a>对用户进行身份验证

测试以下方案, 无论您的 .osc 提供程序是否支持基本身份验证或基于表单的身份验证。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|首次登录。  <br/> |用户可以成功登录到社交网络。  <br/> |
|使用由各种字符 (包括标点符号和 Unicode 字符) 组成的密码登录。  <br/> |用户可以成功登录到社交网络, 而不依赖于密码中使用的字符类型。  <br/> |
|显示用户名或 ID 的**社交网络帐户**的对话框。  <br/> |用户成功登录到网络后,**社会网络帐户**的 .osc 的对话框将显示已登录的用户名或 ID。  <br/> |
|身份验证失败。  <br/> |.osc 显示错误 "**用户名" 或 "密码" 无效**。  <br/> |
|无法连接到社交网络。  <br/> |.osc 显示错误**服务器找不**到。  <br/> |
|能够检索项目。  <br/> |用户通过身份验证后, 应允许所有活动。 获取朋友的数据或活动没有任何错误。  <br/> |
|在重新启动 Outlook 后登录到社交网络。  <br/> |如果 .osc 提供程序允许对密码进行缓存, 则在用户首次进行身份验证后, 只要 .osc 尝试从社交网络获取数据, 就不会再提示用户输入凭据。  <br/> |
   
此外, 如果您的您的 .osc 提供商支持基于表单的身份验证, 也要测试以下方案。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|从调用[ISocialSession:: GetLogonUrl](isocialsession-getlogonurl.md)中获取用户用于登录表单的 URL 的 .osc。  <br/> |.osc 在用户的默认浏览器中打开 URL, 网页允许用户输入凭据以登录到社交网络。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [功能 XML 元素](capabilities-xml-elements.md)  
- [基本身份验证](basic-authentication.md) 
- [基于表单的身份验证](forms-based-authentication.md)
- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

