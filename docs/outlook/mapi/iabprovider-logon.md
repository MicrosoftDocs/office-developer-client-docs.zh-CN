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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 59c6d4a05c91511ad8c481fd4ddbe42396442190
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348781"
---
# <a name="iabproviderlogon"></a>IABProvider::Logon

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
建立与活动会话的连接。
  
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
  
> [in]指向通讯簿提供程序的支持对象的指针。
    
 _ulUIParam_
  
> [in]Logon 方法显示的登录对话框的父窗口句柄（如果允许）。 _ulUIParam_ 参数包含在上一次调用 [MAPILogonEx](mapilogonex.md)函数时传递给 MAPI 的同名参数的值。 
    
 _lpszProfileName_
  
> [in]指向会话配置文件名称的指针。
    
 _ulFlags_
  
> [in]控制如何执行登录的标志的位掩码。 可以设置以下标志：
    
AB_NO_DIALOG 
  
> 提供程序不应在登录期间显示对话框。 如果未设置此标志，提供程序可以显示一个对话框，提示用户输入缺少的配置信息。
    
MAPI_DEFERRED_ERRORS 
  
> 使 **登录** 能够成功返回（可能在登录过程完成之前）。 
    
MAPI_UNICODE 
  
> 所有字符串都应采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串应为 ANSI 格式。
    
 _lpulcbSecurity_
  
> [in， out]指向  _lppbSecurity_ 参数指向的安全凭据结构的大小（以字节为单位）的指针。 在输入时，值必须为非零值;输出时，该值必须为零。 在这两种情况下，指针都必须有效。 
    
 _lppbSecurity_
  
> [in， out]指向指向安全凭据的指针的指针。 在输入时，值必须为非零值;输出时，该值必须为零。 在这两种情况下，指针都必须有效。
    
 _lppMAPIError_
  
> [out]指向指向 [MAPIERROR 结构的指针的](mapierror.md) 指针。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
 _lppABLogon_
  
> [out]指向指向提供程序登录对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立与活动会话的连接。
    
MAPI_E_FAILONEPROVIDER 
  
> 提供程序无法登录，但 MAPI 可以继续在提供程序所属的邮件服务中登录其他提供程序。 
    
MAPI_E_UNCONFIGURED 
  
> 提供程序没有足够的信息来完成登录。 MAPI 调用提供程序的邮件服务条目函数。
    
MAPI_E_UNKNOWN_CPID 
  
> 服务器未配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 服务器未配置为支持客户端区域设置信息。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击登录对话框中的"取消"按钮来取消操作。 
    
## <a name="remarks"></a>备注

当客户端调用 [IMAPISession：：OpenAddressBook](imapisession-openaddressbook.md) 方法时，与会话配置文件中的每个通讯簿提供程序建立连接。 **OpenAddressBook** 然后调用每个提供程序的 **Logon** 方法。 
  
_lpszProfileName_ 参数指向的配置文件名称显示在用户客户端的字符集内，如 _ulFlags_ 参数中是否存在 MAPI_UNICODE 标志所指示。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 **Logon** 方法的实现中，调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 方法来注册唯一标识符或 [MAPIUID](mapiuid.md) 结构。 每个对象都有一个包含此 **MAPIUID** 的条目标识符。 MAPI 使用 **MAPIUID** 将对象与它的提供程序相匹配。 例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法打开消息用户时 **，OpenEntry** 将检查传入的条目标识符的 **MAPIUID** 部分，并通过通讯簿提供程序注册的 **MAPIUID** 进行匹配。 
  
如果客户端多次登录提供程序，你可能希望针对每次登录注册不同的 **MAPIUID。** 通过注册唯一 **MAPIUID** 结构，MAPI 可以正确地将请求路由到相应的提供程序实例。 但是，你可能希望让每个登录对象共享一 **个 MAPIUID**。 在这种情况下，你必须能够自己处理路由，而不是依赖 MAPI。 若要详细了解如何创建 **MAPIUID，** 请参阅注册 [服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。
  
MAPI 传递给 _lpMAPISup_ 参数中的 **Logon** 方法的支持对象提供对 [IMAPISupport ： IUnknown](imapisupportiunknown.md)接口中包含的许多方法的访问。 MAPI 创建根据提供程序类型自定义的支持对象。 例如，如果在建立连接时需要登录到基础消息系统或目录服务，可以调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法来检索此特定登录会话的安全凭据。 
  
如果 **登录** 成功，请确保调用支持对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法来增加其引用计数。 这样，提供程序可以保留会话其余部分的支持对象指针。 如果不调用此 **AddRef** 方法，MAPI 将卸载您的提供程序。 
  
您可以在错误对话框、登录屏幕或其他用户界面中包括  _lpszProfileName_ 参数中传递的配置文件名称。 若要使用配置文件名称，请将其复制到已分配的存储。 
  
创建登录对象，在  _lppABLogon_ 参数中返回指向该对象的指针。 MAPI 使用此登录对象调用 [IABLogon](iablogoniunknown.md) 实现中的方法。 
  
如果在登录过程中需要密码，则仅在未设置登录AB_NO_DIALOG显示登录对话框。 如果用户取消登录过程，通常通过单击对话框中的"取消"按钮，从 **"MAPI_E_USER_CANCEL"返回" 取消"。**
  
通常，当通讯簿提供程序无法登录时，MAPI 将禁用出现故障的提供程序所属的邮件服务，即 MAPI 不会尝试在会话生存期的其余部分为属于该服务的其他任何提供程序建立连接。 但是，如果您的提供程序无法建立连接，并且您不想禁用整个服务，请返回 MAPI_E_FAILONEPROVIDER 或 MAPI_E_UNCONFIGURED。 MAPI 不会禁用提供程序所属的邮件服务。 
  
如果MAPI_E_FAILONEPROVIDER严重到足以阻止邮件服务中其他提供程序建立连接的错误，则返回此代码。 如果MAPI_E_UNCONFIGURED缺少必需的配置信息，并且无法显示对话框来提示用户，则返回此参数。 MAPI 将调用提供程序的邮件服务入口点函数（将 MSG_SERVICE_CONFIGURE 设置为  _ulContext_ 参数）来响应，使服务有机会以编程方式或通过使用 属性表 配置自身。 邮件服务入口点函数完成后，MAPI 将重试登录。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::Logoff](iablogon-logoff.md)
  
[IABLogon::OpenEntry](iablogon-openentry.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IABProvider : IUnknown](iabprovideriunknown.md)

