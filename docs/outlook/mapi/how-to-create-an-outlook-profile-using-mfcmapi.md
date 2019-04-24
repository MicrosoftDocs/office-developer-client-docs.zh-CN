---
title: 使用 MFCMAPI 创建 Outlook 配置文件
ms.date: 05/18/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 85581bc7-2d81-46af-8836-adef39c933fc
description: MFCMAPI 提供对 mapi 存储的访问权限, 以促进 Exchange 和 Outlook 问题的调查, 并为开发人员提供对 mapi 开发的支持。
ms.openlocfilehash: 8a300ad53918b22cc3de5554a1e3c29289cd9365
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345988"
---
# <a name="create-an-outlook-profile-using-mfcmapi"></a>使用 MFCMAPI 创建 Outlook 配置文件

MFCMAPI 提供对 mapi 存储的访问权限, 以促进 Exchange 和 Outlook 问题的调查, 并为开发人员提供对 mapi 开发的支持。

**适用于**：Office 365 | Outlook | Outlook 2016 
  
对于非开发人员, 建议使用 Outlook 用户界面创建 Exchange 2013 的配置文件。
  
## <a name="configure-an-outlook-profile-using-mfcmapi"></a>使用 MFCMAPI 配置 Outlook 配置文件

1. 打开[MFCMAPI](https://mfcmapi.codeplex.com/), 在 "**配置文件**" 菜单上, 单击 "**显示配置文件**"。 
    
2. 在 "**操作**" 菜单上, 单击 "**创建配置文件**"。 
    
3. 为该配置文件创建一个新名称, 然后单击 **"确定"**。 
    
4. 右键单击新的配置文件, 然后在 "**服务**" 菜单上单击 "**添加服务**"。 
    
5. 取消选中 "显示服务 UI" 框, 然后单击 **"确定**"。 
    
6. 双击新创建的配置文件, 然后单击**MSEMS**服务。 
    
7. 找到 "Exchange 配置文件" 部分。
    
   这在 Outlook 的 MAPI 中可能有困难，因为在 2010 及以上版本均不再设有全局配置文件部分。 要找到配置文件部分，需找到属性 PR_EMSMDB_SECTION_UID (0x3D150102)。 该值为配置文件部分的 GUID，采用二进制形式，后续步骤将使用该值。 您将在步骤9中需要此值。
    
8. 双击**MSEMS**服务。 
    
9. 使用步骤7中的 UID 查找 " **Exchange**配置文件" 部分, 然后单击以选择该行。 
    
10. 在 "属性" 菜单上, 单击 "**其他属性**"。 
    
11. 单击 "**添加**", 然后添加以下属性: 
    
    **对于 Outlook 2016**: `PR_PROFILE_USER_SMTP_EMAIL_ADDRESS_W (0x6641001F)`和`PR_DISPLAY_NAME_W`
    
    **对于适用于 Office 的 Outlook 365** `PR_PROFILE_UNRESOLVED_NAME`: `PR_ROH_PROXY_SERVER`、 `PR_ROH_FLAGS` `PR_ROH_PROXY_AUTH_SCHEME` `PR_PROFILE_AUTH_PACKAGE` `PR_PROFILE_UNRESOLVED_SERVER`、、、、和`PR_ROH_PROXY_PRINCIPAL_NAME` 
    
    **对于 Exchange 2013**: `PR_PROFILE_UNRESOLVED_NAME`、 `PR_PROFILE_UNRESOLVED_SERVER` `PR_ROH_PROXY_SERVER` `PR_ROH_FLAGS` `PR_ROH_PROXY_AUTH_SCHEME`、、、和`PR_PROFILE_AUTH_PACKAGE`。 
    
12. 单击 **"确定"**, 然后根据下表配置每个属性, 具体取决于要连接到的版本。 
    
13. 在 "**会话**" 菜单上, 单击 "**登录和显示存储**", 然后选择配置文件 (如果尚未选中)。 
    
### <a name="outlook-2016"></a>Outlook 2016
  
||||
|:-----|:-----|:-----|
|**Property** <br/> |**Tag** <br/> |**Description** <br/> |
| PR_PROFILE_USER_SMTP_EMAIL_ADDRESS_W  <br/> |0x6641001F  <br/> |用户的 SMTP 地址  <br/> |
|PR_DISPLAY_NAME_W  <br/> |0x3001001F  <br/> |用户的显示名称  <br/> |
|PR_STORE_PROVIDERS  <br/> |0x3D000102  <br/> |配置此属性的值, 该属性位于 " **EMSMDB** " 部分, 并为匹配属性更新相应的 UID  <br/> |
   
### <a name="outlook-for-office-365"></a>Outlook for Office 365
  
||||
|:-----|:-----|:-----|
|**属性** <br/> |**Value** <br/> |**说明** <br/> |
|PR_PROFILE_UNRESOLVED_NAME<sup>1</sup> <br/> |邮箱别名  <br/> |目标邮箱的别名;例如, 管理员  <br/> |
|PR_PROFILE_UNRESOLVED_SERVER<sup>1</sup> <br/> |个性化服务器 id  <br/> |从**自动发现**中检索到的值。 格式<guid>@tenant。 onmicrosoft.com;例如, F5FA2827-5978-43cd-8FA8-E07BC3BB5591@contoso.onmicrosoft.com  <br/>  *自动发现节点*: 响应/帐户/协议/服务器 (EXCH)  <br/> |
|PR_ROH_PROXY_SERVER  <br/> |outlook.office365.com  <br/> | *自动发现节点*: 响应/帐户/协议/服务器 (EXPR) <sup>2</sup> <br/> |
|PR_ROH_FLAGS  <br/> |ROHFLAGS_USE_ROH (0x1)  <br/> ROH_FLAGS_USE_SSL (0x2)  <br/>  ROHFLAGS_MUTUAL_AUTH (0x4)  <br/>  ROHFLAGS_HTTP_FIRST_ON_FAST (0x8)  <br/>  ROHFLAGS_HTTP_FIRST_ON_SLOW (0x20)  <br/> |包含 Outlook 用于通过使用超文本传输协议 (HTTP) 上的远程过程调用 (RPC) 连接到 Microsoft Exchange Server 的配置文件中的设置。 *自动发现节点*: 响应/帐户/协议/SSL (EXPR) <sup>2</sup> <br/> |
| PR_ROH_PROXY_AUTH_SCHEME  <br/> | RPC_C_HTTP_AUTHN_SCHEME_BASIC (0x1)  <br/> |表示要用于此配置文件*自动发现节点*的身份验证协议: Response/Account/protocol/AuthPackage (EXPR) <sup>2</sup> <br/> |
|PR_PROFILE_AUTH_PACKAGE  <br/> |RPC_C_AUTHN_NONE (0x0)  <br/> |介绍用于 RPC*自动发现节点*的身份验证方案: Response/Account/Protocol/AuthPackage (EXCH)) <sup>3</sup> <br/> |
|PR_ROH_PROXY_PRINCIPAL_NAME  <br/> |CertPrincipalName 元素  <br/> |用于支持相互身份验证;例如, msstd:outlook "*自动发现" 节点*: Response/Account/Protocol/CertPrincipalName (EXPR)) <sup>2</sup> <br/> |
   
### <a name="exchange-2013"></a>Exchange 2013
  
||||
|:-----|:-----|:-----|
|**属性** <br/> |**Value** <br/> |**说明** <br/> |
|PR_PROFILE_UNRESOLVED_NAME<sup>1</sup> <br/> |邮箱别名  <br/> |目标邮箱的别名;例如, 管理员  <br/> |
|PR_PROFILE_UNRESOLVED_SERVER<sup>1</sup> <br/> |个性化服务器 id  <br/> |从**自动发现**中检索到的值。 格式<guid>@tenant。 onmicrosoft.com;例如, F5FA2827-5978-43cd-8FA8-E07BC3BB5591@contoso.onmicrosoft.com  <br/>  *自动发现节点*: 响应/帐户/协议/服务器 (EXCH)  <br/> |
|PR_ROH_PROXY_SERVER  <br/> | 客户端访问服务器域名称  <br/> | 完全限定的域名 (FQDN);例如, e2013cas.contoso.com*自动发现节点*: 响应/帐户/协议/服务器 (EXPR) <sup>2</sup> <br/> |
|PR_ROH_FLAGS  <br/> |ROHFLAGS_USE_ROH (0x1)  <br/>  ROHFLAGS_HTTP_FIRST_ON_FAST (0x8)  <br/> ROHFLAGS_HTTP_FIRST_ON_SLOW (0x20))  <br/> |包含 Outlook 使用远程过程调用 (RPC) 和超文本传输协议 (HTTP)*自动发现节点*连接到 Microsoft Exchange Server 时使用的配置文件中的设置: 响应/帐户/协议/SSL (EXPR) <sup>2</sup> <br/> |
| PR_ROH_PROXY_AUTH_SCHEME  <br/> | RPC_C_HTTP_AUTHN_SCHEME_NTLM (0x2)  <br/> |表示要用于此配置文件*自动发现节点*的身份验证协议: Response/Account/protocol/AuthPackage (EXPR) <sup>2</sup> <br/> |
|PR_PROFILE_AUTH_PACKAGE  <br/> |RPC_C_AUTHN_WINNT (0xA)  <br/> |介绍用于 RPC*自动发现节点*的身份验证方案: Response/Account/Protocol/AuthPackage (EXCH)) <sup>3</sup> <br/> |
   
> [!NOTE] 
> - 以上提到的所有属性值可能因特定组织而异。 
> - <sup>1</sup>您必须使用 Unicode 版本, 而不是 ANSI 版本。 
> - 您必须使用基于旧 XML (POX) 的自动发现。 这是配置 Outlook/Exchange 配置文件的唯一受支持的自动发现。
> - 您可以通过右键单击**系统托盘**中的 Outlook 图标, 同时按住 CTRL 并单击 "**测试电子邮件自动配置**", 使用 Outlook 为您发出自动发现请求。 
> - 对于 PR_ROH_FLAGS, 您的环境可能需要标志 ROHFLAGS_SSL_ONLY (0x2) 来通知 MAPI 仅使用 SSL。 如果您的环境需要进行相互身份验证, 则需要将该标志设置为 [ROHFLAGS_MUTUAL_AUTH (0x4)]。 设置 ROHFLAGS_MUTUAL_AUTH (0x4) 将要求您同时设置 PR_ROH_PROXY_PRINCIPAL_NAME 属性。 应将此设置为服务器的主体名称。
> - <sup>2</sup>对于 Outlook 2010, 您将需要使用 EXPR 协议。 Outlook 2013 使用 EXHTTP 协议。 
> - <sup>3</sup>此值可能不在自动发现响应中。 如果未指定, 客户端应使用 Kerberos 或 NTLM。 
    
有关故障排除提示, 请参阅 how [to configure a Outlook profile using MFCMAPI for Exchange 2013](https://blogs.msdn.microsoft.com/dvespa/2014/01/16/how-to-configure-an-outlook-profile-using-mfcmapi-for-exchange-2013)。
  
## <a name="see-also"></a>另请参阅

- [Outlook MAPI 引用](https://msdn.microsoft.com/library/office/cc765775.aspx)  
- [在 Outlook 中以编程方式创建配置文件](https://msdn.microsoft.com/library/office/mt707568.aspx)
    

