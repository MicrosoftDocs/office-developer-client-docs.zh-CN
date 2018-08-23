---
title: IABProviderLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABProvider.Logon
api_type:
- COM
ms.assetid: f9468715-1674-4d14-81c8-2f24dbaa0453
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8cb7934919722139622b6caf3aac741c9b2e54c5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582460"
---
# <a name="iabproviderlogon"></a>IABProvider::Logon

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
建立到活动会话的连接。
  
```cpp
HRESULT Logon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG ulFlags,
  ULONG FAR * lpulcbSecurity,
  LPBYTE FAR * lppbSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPABLOGON FAR * lppABLogon
);
```

## <a name="parameters"></a>参数

 _lpMAPISup_
  
> [in]指向地址簿提供程序的支持对象的指针。
    
 _ulUIParam_
  
> [in]**Logon**方法显示，如果允许的登录对话框中的父窗口句柄。 _UlUIParam_参数包含在以前的呼叫[MAPILogonEx](mapilogonex.md)函数传递给 MAPI 具有相同名称的参数的值。 
    
 _lpszProfileName_
  
> [in]一个指向会话配置文件的名称。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何执行登录。 可以设置以下标志：
    
AB_NO_DIALOG 
  
> 提供程序不应在登录过程中显示一个对话框。 如果未设置此标志，提供程序可以显示一个对话框，提示用户缺少的配置信息。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**登录**成功返回，可能之前完成登录过程。 
    
MAPI_UNICODE 
  
> 所有字符串都应为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，则字符串应以 ANSI 格式。
    
 _lpulcbSecurity_
  
> [传入、 传出]指向的大小，以字节为单位_lppbSecurity_参数指向的安全凭据结构的指针。 在输入的值必须是非零值;输出，则必须为零。 在这两种情况下，必须是有效的指针。 
    
 _lppbSecurity_
  
> [传入、 传出]指向安全凭据的指针的指针。 在输入的值必须是非零值;输出，则必须为零。 在这两种情况下必须是有效的指针。
    
 _lppMAPIError_
  
> [输出]指向[MAPIERROR](mapierror.md)结构的指针的指针。 如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。 
    
 _lppABLogon_
  
> [输出]指向提供程序的登录对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立与活动会话的连接。
    
MAPI_E_FAILONEPROVIDER 
  
> 提供程序不能登录，但 MAPI 可以继续登录提供程序所属的消息服务中的其他提供程序。 
    
MAPI_E_UNCONFIGURED 
  
> 提供程序没有足够的信息，完成登录。 MAPI 调用的提供程序的消息服务条目函数。
    
MAPI_E_UNKNOWN_CPID 
  
> 将服务器不配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 将服务器不配置为支持客户端的区域设置信息。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击登录对话框中的**取消**按钮。 
    
## <a name="remarks"></a>注解

连接被建立与每个地址簿提供商会话配置文件中，当客户端调用[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)方法。 **OpenAddressBook**然后调用每个提供程序的**登录**方法。 
  
_LpszProfileName_参数指向的配置文件名称显示在用户的客户端通过状态或缺少 MAPI_UNICODE 标志_ulFlags_参数中所示的字符集。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

在您的**登录**方法的实现，调用注册的唯一标识符或[MAPIUID](mapiuid.md)结构的[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法。 每个对象都有包含此**MAPIUID**条目标识符。 MAPI 使用**MAPIUID**以匹配具有其提供程序的对象。 例如，当客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法打开邮件用户， **OpenEntry**检查已传递中并与注册的**MAPIUID**相匹配时它的项标识符的**MAPIUID**部分通讯簿提供程序。 
  
如果客户端登录到您的提供商多次，可能要注册的每次登录不同**MAPIUID** 。 注册唯一**MAPIUID**结构启用 MAPI 以正确将请求路由到相应的提供程序实例。 但是，您可能希望共享一个**MAPIUID**每个登录对象。 在这种情况下，您必须能够处理路由而不是依赖 MAPI 自己。 有关如何创建**MAPIUID**的详细信息，请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。
  
MAPI 将传递给_lpMAPISup_参数中您**登录**方法支持对象提供许多中包含的方法的访问[IMAPISupport: IUnknown](imapisupportiunknown.md)接口。 MAPI 创建支持对象为提供程序类型的自定义。 例如，如果您需要登录到基础邮件系统或目录服务建立连接时，您可以调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法检索该特定登录会话的安全凭据。 
  
如果成功**登录**，请确保您调用支持对象的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法，以增加引用计数。 这使您提供程序留会话的其余部分的支持对象指针。 如果您不调用此**AddRef**方法，MAPI 将卸载您的提供商。 
  
您可以包括在错误对话框、 登录屏幕或其他用户界面中_lpszProfileName_参数中传递的配置文件名称。 若要使用的配置文件名称，将其复制到已分配的存储。 
  
创建登录对象并返回到此_lppABLogon_参数中的指针。 MAPI 使用该登录对象以使在[IABLogon](iablogoniunknown.md)实现对方法的调用。 
  
如果您在登录过程中需要密码，显示登录对话框中，仅当未设置 AB_NO_DIALOG 标志。 如果用户取消了登录过程，通常通过单击对话框中的**取消**按钮返回 MAPI_E_USER_CANCEL 从**登录**。
  
通常，当通讯簿提供程序不能登录，MAPI 禁用邮件服务的失败提供程序所属 — 即，MAPI 不会尝试建立连接的任何所属的会话的 rest 服务的其他提供程序生存期。 但是，如果您不希望禁用整个服务提供程序无法建立连接，返回 MAPI_E_FAILONEPROVIDER 或 MAPI_E_UNCONFIGURED。 MAPI 不会禁用邮件服务提供程序所属。 
  
返回 MAPI_E_FAILONEPROVIDER 如果出现错误，则不严重，阻止邮件服务中的其他提供程序建立连接。 如果从配置文件缺少必需的配置信息，您无法显示一个对话框，提示用户，则返回 MAPI_E_UNCONFIGURED。 MAPI 将响应通过 MSG_SERVICE_CONFIGURE 设置提供程序的消息服务入口点函数调用作为_ulContext_参数以使服务本身，或者以编程方式配置有机会或使用属性表中。 当邮件服务入口点函数已完成，MAPI 重试登录。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::Logoff](iablogon-logoff.md)
  
[IABLogon::OpenEntry](iablogon-openentry.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IABProvider : IUnknown](iabprovideriunknown.md)

