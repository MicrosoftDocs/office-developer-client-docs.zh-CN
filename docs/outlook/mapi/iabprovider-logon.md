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
  
> 实时指向通讯簿提供程序的支持对象的指针。
    
 _ulUIParam_
  
> 实时**登录**方法显示登录对话框的父窗口的句柄 (如果允许)。 _ulUIParam_参数包含在以前对[MAPILogonEx](mapilogonex.md)函数的调用中传递给 MAPI 的同名参数的值。 
    
 _lpszProfileName_
  
> 实时指向会话配置文件的名称的指针。
    
 _ulFlags_
  
> 实时用于控制登录执行方式的标志的位掩码。 可以设置以下标志:
    
AB_NO_DIALOG 
  
> 提供程序在登录过程中不应显示对话框。 如果未设置此标志, 则提供程序可以显示一个对话框, 提示用户缺少配置信息。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**登录**成功返回, 可能在登录过程完成前。 
    
MAPI_UNICODE 
  
> 所有字符串都应采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串应为 ANSI 格式。
    
 _lpulcbSecurity_
  
> [in, out]指向由_lppbSecurity_参数指向的安全凭据结构的大小 (以字节为单位) 的指针。 在输入时, 值必须为非零值。在输出时, 值必须为零。 在这两种情况下, 指针必须有效。 
    
 _lppbSecurity_
  
> [in, out]指向指向安全凭据的指针的指针。 在输入时, 值必须为非零值。在输出时, 值必须为零。 在这两种情况下, 指针必须有效。
    
 _lppMAPIError_
  
> 排除指向指向[MAPIERROR](mapierror.md)结构的指针的指针。 如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
 _lppABLogon_
  
> 排除指向提供程序的登录对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立与活动会话的连接。
    
MAPI_E_FAILONEPROVIDER 
  
> 提供程序无法登录, 但 MAPI 可以继续登录到提供程序所属的邮件服务中的其他提供程序。 
    
MAPI_E_UNCONFIGURED 
  
> 提供程序提供的信息不足, 无法完成登录。 MAPI 调用提供程序的邮件服务条目函数。
    
MAPI_E_UNKNOWN_CPID 
  
> 未将服务器配置为支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID 
  
> 未将服务器配置为支持客户端的区域设置信息。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击登录对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

当客户端调用[IMAPISession:: OpenAddressBook](imapisession-openaddressbook.md)方法时, 将与会话配置文件中的每个通讯簿提供程序建立连接。 然后, **OpenAddressBook**调用每个提供程序的**登录**方法。 
  
由_lpszProfileName_参数指向的配置文件名称以用户客户端的字符集的形式显示, 如_ulFlags_参数中是否存在 MAPI_UNICODE 标志所指示。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在您的**登录**方法实现中, 调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法以注册一个唯一的标识符或[MAPIUID](mapiuid.md)结构。 您的每个对象都具有包含此**MAPIUID**的条目标识符。 MAPI 使用**MAPIUID**将对象与其提供程序相匹配。 例如, 当客户端调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法打开邮件用户时, **OpenEntry**会检查传入的条目标识符的**MAPIUID**部分, 并将其与注册的**MAPIUID**通讯簿提供程序。 
  
如果客户端多次登录到您的提供程序, 则可能需要为每个登录注册一个不同的**MAPIUID** 。 注册唯一的**MAPIUID**结构使 MAPI 能够将请求正确路由到相应的提供程序实例。 但是, 您可能希望让每个登录对象共享一个**MAPIUID**。 在这种情况下, 您必须能够自己处理路由, 而不是依赖 MAPI。 有关如何创建**MAPIUID**的详细信息, 请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。
  
MAPI 传递给_lpMAPISup_参数中的**登录**方法的支持对象提供了对[IMAPISupport: IUnknown](imapisupportiunknown.md)接口中包含的许多方法的访问权限。 MAPI 创建一个支持对象, 该对象自定义为您的提供程序类型。 例如, 如果您需要在建立连接时登录到基础邮件系统或目录服务, 则可以调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法来检索此特定登录会话的安全凭据。 
  
如果**登录**成功, 请确保调用支持对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法以增加其引用计数。 这使提供程序能够在会话的其余部分中保持支持对象指针。 如果您不调用此**AddRef**方法, MAPI 将卸载您的提供程序。 
  
可以在错误对话框、登录屏幕或其他用户界面中包括在_lpszProfileName_参数中传递的配置文件名称。 若要使用配置文件名称, 请将其复制到已分配的存储中。 
  
创建一个登录对象, 并在_lppABLogon_参数中返回指向它的指针。 MAPI 使用此登录对象对[IABLogon](iablogoniunknown.md)实现中的方法进行调用。 
  
如果在登录过程中需要密码, 则仅当未设置 AB_NO_DIALOG 标志时, 才会显示 "登录" 对话框。 如果用户取消登录过程, 通常是单击对话框中的 "**取消**" 按钮, 将 MAPI_E_USER_CANCEL 从**登录**返回。
  
通常, 当通讯簿提供商无法登录时, mapi 将禁用失败的提供程序所属的邮件服务, 即 mapi 将不会尝试为属于该服务的其他任何其他提供程序建立与该会话的其余部分的连接lifetime. 但是, 如果您的提供商无法建立连接, 而您希望不禁用整个服务, 则返回 MAPI_E_FAILONEPROVIDER 或 MAPI_E_UNCONFIGURED。 MAPI 不会禁用提供程序所属的邮件服务。 
  
如果发生的错误不足以阻止邮件服务中的其他提供程序建立连接, 则返回 MAPI_E_FAILONEPROVIDER。 如果配置文件中缺少必要的配置信息, 则返回 MAPI_E_UNCONFIGURED, 并且无法显示对话框以提示用户。 MAPI 将通过调用 MSG_SERVICE_CONFIGURE 设置为_ulContext_参数的提供程序的邮件服务入口点函数来做出响应, 从而使服务有机会以编程方式或使用属性表配置自身。 当邮件服务入口点函数完成时, MAPI 将重试登录。 
  
## <a name="see-also"></a>另请参阅



[IABLogon::Logoff](iablogon-logoff.md)
  
[IABLogon::OpenEntry](iablogon-openentry.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IABProvider : IUnknown](iabprovideriunknown.md)

