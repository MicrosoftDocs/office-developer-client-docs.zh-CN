---
title: 使用 MFCMAPI 创建 Outlook 配置文件
ms.date: 05/18/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 85581bc7-2d81-46af-8836-adef39c933fc
description: MFCMAPI 提供对 MAPI 存储以加快调查的 Exchange 和 Outlook 问题和开发人员提供支持的 MAPI 开发访问。
ms.openlocfilehash: 8df9a4c2783829b7f3540046daecb12ce0b6b86a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775094"
---
# <a name="create-an-outlook-profile-using-mfcmapi"></a>使用 MFCMAPI 创建 Outlook 配置文件

MFCMAPI 提供对 MAPI 存储以加快调查的 Exchange 和 Outlook 问题和开发人员提供支持的 MAPI 开发访问。

**适用于**：Office 365 | Outlook | Outlook 2016 
  
对于非开发人员，建议使用 Outlook 用户界面创建 Exchange 2013 配置文件。
  
## <a name="configure-an-outlook-profile-using-mfcmapi"></a>配置 Outlook 配置文件使用 MFCMAPI

1. 打开[MFCMAPI](https://mfcmapi.codeplex.com/)，并在**配置文件**菜单上，单击**显示配置文件**。 
    
2. 在**操作**菜单中，单击**创建配置文件**。 
    
3. 创建配置文件的新名称，然后单击**确定**。 
    
4. 右键单击新的配置文件，然后在**服务**菜单上，单击**添加服务**。 
    
5. 取消选中"显示服务 UI"框中，，然后单击**确定**。 
    
6. 双击新建配置文件，然后单击**MSEMS**服务。 
    
7. 找到 Exchange 配置文件部分。
    
   这在 Outlook 的 MAPI 中可能有困难，因为在 2010 及以上版本均不再设有全局配置文件部分。 要找到配置文件部分，需找到属性 PR_EMSMDB_SECTION_UID (0x3D150102)。 该值为配置文件部分的 GUID，采用二进制形式，后续步骤将使用该值。 您将需要在步骤 9 中的此值。
    
8. 双击**MSEMS**服务。 
    
9. 使用步骤 7 中的 UID 查找**Exchange**配置文件部分，然后单并单击以选择该行。 
    
10. 在属性菜单中，单击**其他属性**。 
    
11. 单击**添加**，然后添加以下属性： 
    
    **为 Outlook 2016**:`PR_PROFILE_USER_SMTP_EMAIL_ADDRESS_W (0x6641001F)`和`PR_DISPLAY_NAME_W`
    
    **为 Outlook for Office 365**: `PR_PROFILE_UNRESOLVED_NAME`， `PR_PROFILE_UNRESOLVED_SERVER`， `PR_ROH_PROXY_SERVER`， `PR_ROH_FLAGS`， `PR_ROH_PROXY_AUTH_SCHEME`， `PR_PROFILE_AUTH_PACKAGE`，和`PR_ROH_PROXY_PRINCIPAL_NAME` 
    
    **Exchange 2013**: `PR_PROFILE_UNRESOLVED_NAME`， `PR_PROFILE_UNRESOLVED_SERVER`， `PR_ROH_PROXY_SERVER`， `PR_ROH_FLAGS`， `PR_ROH_PROXY_AUTH_SCHEME`，和`PR_PROFILE_AUTH_PACKAGE`。 
    
12. 单击**确定**，然后配置根据下表根据您要连接到的版本的每个属性。 
    
13. 在**会话**菜单上，单击**登录和显示存储**和 （如果尚未选中），然后选择的配置文件。 
    
### <a name="outlook-2016"></a>Outlook 2016
  
||||
|:-----|:-----|:-----|
|**属性** <br/> |**Tag** <br/> |**说明** <br/> |
| PR_PROFILE_USER_SMTP_EMAIL_ADDRESS_W  <br/> |0x6641001F  <br/> |用户的 SMTP 地址  <br/> |
|PR_DISPLAY_NAME_W  <br/> |0x3001001F  <br/> |用户的显示名称  <br/> |
|PR_STORE_PROVIDERS  <br/> |0x3D000102  <br/> |配置位于**EMSMDB**部分中，此属性的值和更新的匹配属性的相应 UID  <br/> |
   
### <a name="outlook-for-office-365"></a>Office 365 的 outlook
  
||||
|:-----|:-----|:-----|
|**属性** <br/> |**值** <br/> |**说明** <br/> |
|PR_PROFILE_UNRESOLVED_NAME<sup>1</sup> <br/> |邮箱别名  <br/> |目标邮箱中; 的别名例如，管理员  <br/> |
|PR_PROFILE_UNRESOLVED_SERVER<sup>1</sup> <br/> |个性化的服务器 id  <br/> |检索从**自动发现**的值。 格式<guid>@tenant.onmicrosoft.com;例如，F5FA2827-5978-43cd-8FA8-E07BC3BB5591@contoso.onmicrosoft.com  <br/>  *自动发现节点*： 响应/帐户/协议/服务器 (EXCH)  <br/> |
|PR_ROH_PROXY_SERVER  <br/> |outlook.office365.com  <br/> | *自动发现节点*： 响应/帐户/协议/服务器 (EXPR) <sup>2</sup> <br/> |
|PR_ROH_FLAGS  <br/> |ROHFLAGS_USE_ROH (0X1)  <br/> ROH_FLAGS_USE_SSL (0X2)  <br/>  ROHFLAGS_MUTUAL_AUTH (0X4)  <br/>  ROHFLAGS_HTTP_FIRST_ON_FAST (0X8)  <br/>  ROHFLAGS_HTTP_FIRST_ON_SLOW (0X20)  <br/> |包含 Outlook 用于使用远程过程调用 (RPC) 通过超文本传输协议 (HTTP) 连接到 Microsoft Exchange Server 配置文件中的设置。 *自动发现节点*： 响应/帐户/协议/SSL (EXPR) <sup>2</sup> <br/> |
| PR_ROH_PROXY_AUTH_SCHEME  <br/> | RPC_C_HTTP_AUTHN_SCHEME_BASIC (0X1)  <br/> |代表要用于此配置文件*自动发现节点*的身份验证协议： 响应/帐户/协议/AuthPackage (EXPR) <sup>2</sup> <br/> |
|PR_PROFILE_AUTH_PACKAGE  <br/> |RPC_C_AUTHN_NONE (0X0)  <br/> |介绍用于 RPC*自动发现节点*的身份验证方案： 响应/帐户/协议/AuthPackage (EXCH)) <sup>3</sup> <br/> |
|PR_ROH_PROXY_PRINCIPAL_NAME  <br/> |CertPrincipalName 元素  <br/> |使用支持相互身份验证;例如，msstd:outlook.com*自动发现节点*： 响应/帐户/协议/CertPrincipalName (EXPR)) <sup>2</sup> <br/> |
   
### <a name="exchange-2013"></a>Exchange 2013
  
||||
|:-----|:-----|:-----|
|**属性** <br/> |**值** <br/> |**说明** <br/> |
|PR_PROFILE_UNRESOLVED_NAME<sup>1</sup> <br/> |邮箱别名  <br/> |目标邮箱中; 的别名例如，管理员  <br/> |
|PR_PROFILE_UNRESOLVED_SERVER<sup>1</sup> <br/> |个性化的服务器 id  <br/> |检索从**自动发现**的值。 格式<guid>@tenant.onmicrosoft.com;例如，F5FA2827-5978-43cd-8FA8-E07BC3BB5591@contoso.onmicrosoft.com  <br/>  *自动发现节点*： 响应/帐户/协议/服务器 (EXCH)  <br/> |
|PR_ROH_PROXY_SERVER  <br/> | 客户端访问服务器的域名  <br/> | 完全限定的域名 (FQDN);例如，e2013cas.contoso.com*自动发现节点*： 响应/帐户/协议/服务器 (EXPR) <sup>2</sup> <br/> |
|PR_ROH_FLAGS  <br/> |ROHFLAGS_USE_ROH (0X1)  <br/>  ROHFLAGS_HTTP_FIRST_ON_FAST (0X8)  <br/> ROHFLAGS_HTTP_FIRST_ON_SLOW (0X20))  <br/> |包含由 Outlook*自动发现节点*的超文本传输协议 (HTTP) 通过使用远程过程调用 (RPC) 连接到 Microsoft Exchange Server 配置文件中的设置： 响应/帐户/协议/SSL (EXPR) <sup>2</sup> <br/> |
| PR_ROH_PROXY_AUTH_SCHEME  <br/> | RPC_C_HTTP_AUTHN_SCHEME_NTLM (0X2)  <br/> |代表要用于此配置文件*自动发现节点*的身份验证协议： 响应/帐户/协议/AuthPackage (EXPR) <sup>2</sup> <br/> |
|PR_PROFILE_AUTH_PACKAGE  <br/> |RPC_C_AUTHN_WINNT (0XA)  <br/> |介绍用于 RPC*自动发现节点*的身份验证方案： 响应/帐户/协议/AuthPackage (EXCH)) <sup>3</sup> <br/> |
   
> [!NOTE] 
> - 为组织特定情况下，上面提到的所有属性值可能会都有所不同。 
> - <sup>1</sup>必须使用 Unicode 版本，而不是 ANSI 版本。 
> - 您必须使用普通旧 XML (POX) 基于自动发现。 这是唯一受支持自动发现配置 Outlook/Exchange 配置文件。
> - 您可以使用 Outlook 代表您发起右键 Outlook 图标在**系统任务栏**中，单击时按住 CTRL 并单击**测试电子邮件自动配置**的自动发现请求。 
> - PR_ROH_FLAGS，为您的环境可能需要标志 ROHFLAGS_SSL_ONLY (0x2) 以告知 MAPI 使用仅 SSL。 如果您的环境所需的相互身份验证，您需要设置的标志以及 [ROHFLAGS_MUTUAL_AUTH (0x4)]。 设置 ROHFLAGS_MUTUAL_AUTH (0x4) 将要求您还设置 PR_ROH_PROXY_PRINCIPAL_NAME 的属性。 应设置此服务器的主体名称。
> - <sup>2</sup>的 Outlook 2010 中，您将需要使用 EXPR 协议。 Outlook 2013 使用 EXHTTP 协议。 
> - <sup>3</sup>此值可能不自动发现响应中。 如果未指定，客户应使用 Kerberos 或 NTLM。 
    
疑难解答提示，请参阅[如何配置使用 MFCMAPI Exchange 2013 的 Outlook 配置文件](https://blogs.msdn.microsoft.com/dvespa/2014/01/16/how-to-configure-an-outlook-profile-using-mfcmapi-for-exchange-2013)。
  
## <a name="see-also"></a>另请参阅

- [Outlook MAPI 引用](https://msdn.microsoft.com/en-us/library/office/cc765775.aspx)  
- [在 Outlook 中以编程方式创建一个配置文件](https://msdn.microsoft.com/en-us/library/office/mt707568.aspx)
    

