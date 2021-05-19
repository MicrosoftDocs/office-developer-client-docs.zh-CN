---
title: IXPProviderTransportLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider.TransportLogon
api_type:
- COM
ms.assetid: 534929f2-36a2-463d-8c4c-d86060cde127
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 53b2733dbf38d680027dc00ecf5513f384e46660
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417306"
---
# <a name="ixpprovidertransportlogon"></a>IXPProvider::TransportLogon

**适用于**：Outlook 2013 | Outlook 2016 
  
建立客户端应用程序登录到传输提供程序的会话。 
  
```cpp
HRESULT TransportLogon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG FAR * lpulFlags,
  LPMAPIERROR FAR * lppMAPIError,
  LPXPLOGON FAR * lppXPLogon
);
```

## <a name="parameters"></a>参数

_lpMAPISup_：[in] 指向传输提供程序对此会话的 MAPI 中回调函数的支持对象的指针。 在传输提供程序释放该对象之前，该对象一直有效。
    
_ulUIParam_：[in] 此方法显示的任何对话框或窗口的父窗口的句柄。 _ulUIParam_ 参数可以是非 null 参数，例如，当在 _lpulFlags_ 参数中设置 LOGON_SETUP 标志时。 
    
_lpszProfileName_：[in] 指向用户的配置文件名称的指针。 _lpszProfileName_ 参数主要用于必须显示对话框时。 
    
_lpulFlags_：[in， out] 控制如何建立登录会话的标志的位掩码。 MAPI 后台处理程序可以在输入时设置以下标志：
    
  - LOGON_NO_CONNECT：除了传输和接收邮件外，用户帐户还登录到此传输提供程序。 传输提供程序不应尝试建立与其他邮件系统的任何连接。
        
  - LOGON_NO_DIALOG：即使当前保存的用户凭据无效或无法登录，也不应显示任何对话框。
        
  - LOGON_NO_INBOUND：传输提供程序无需初始化以接收邮件，并且不应接受传入的邮件。 MAPI 后台处理程序稍后可以使用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法向传输提供程序发出信号，以启用传入邮件处理。 
        
  - LOGON_NO_OUTBOUND：传输提供程序无需初始化以发送邮件，因为 MAPI 后台处理程序不提供任何内容。 如果客户端应用程序需要在消息组合期间连接到远程提供程序，以便它可以进行 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法调用，则传输提供程序应建立连接。 MAPI 后台处理程序可以使用 **TransportNotify** 在传出操作开始时向传输提供程序发出信号。 
      
  - MAPI_UNICODE：配置文件名称的传入字符串采用 Unicode 格式。 如果未设置 MAPI \_ UNICODE 标志，则字符串采用 ANSI 格式。
      
    传输提供程序可以在输出上设置以下标志：
      
  - LOGON_SP_IDLE：请求 MAPI 后台处理程序经常调用传输提供程序的 [IXPLogon：：Idle](ixplogon-idle.md) 方法进行空闲时间处理。 
      
  - LOGON_SP_POLL：请求 MAPI 后台处理程序经常对返回的登录对象调用 [IXPLogon：:P oll](ixplogon-poll.md) 方法以检查新邮件。 如果未设置此标志，则 MAPI 后台处理程序仅在传输提供程序使用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法通知后台处理程序有要处理的新消息时检查新邮件。 通过不设置此标志和未通知 MAPI 后台处理程序的邮件接收，传输提供程序实际上变为仅发送。 
      
  - LOGON_SP_RESOLVE：MAPI 后台处理程序解析为完整地址的请求将处理此传输提供程序不支持的收件人的所有邮件地址。 因此，传输提供程序可以构造所有收件人的答复路径。
      
  - [MAPI_UNICODE：MAPIERROR](mapierror.md)结构中返回的字符串（如果有）采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
_lppMAPIError_：[out] 指向返回 **的 MAPIERROR** 结构的指针（如果有），其中包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
_lppXPLogon_：[out] 指向返回的传输提供程序登录对象的指针。
    
## <a name="return-value"></a>返回值

S_OK：调用成功并返回了预期值。
    
MAPI_E_FAILONEPROVIDER：此提供程序无法登录，但此错误不应禁用该服务。 
    
MAPI_E_UNCONFIGURED：配置文件包含的信息不足，无法完成登录。 MAPI 调用提供程序的邮件服务入口点函数。
    
MAPI_E_UNKNOWN_CPID：提供程序无法支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID：提供程序无法支持客户端区域设置信息。
    
MAPI_E_USER_CANCEL：用户通常通过单击对话框中的"取消"按钮来取消操作。  
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IXPProvider：：TransportLogon** 方法为用户建立登录会话。 
  
大多数传输提供程序都使用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法，该方法与  _lpMAPISup_ 参数指向的支持对象一起提供，用于保存和检索用户标识信息、服务器地址和凭据。 通过使用 **OpenProfileSection，** 传输提供程序可以保存任意信息并将其与特定资源的登录关联。 例如，提供程序可以使用 **OpenProfileSection** 保存与特定会话关联的帐户名和密码，以及访问该会话的资源所需的任何服务器名称或其他必要信息。 MAPI 从外部访问隐藏与资源关联的信息。 通过  _lpMAPISup_ 提供的配置文件部分由 MAPI 后台处理程序管理，因此与此用户上下文相关的数据与其他上下文的数据分隔开。 
  
传输提供程序必须对支持对象调用 **IUnknown：：AddRef** 方法，并保留指向此对象的指针副本作为提供程序登录对象的一部分。 
  
提供了显示名称  _lpszProfileName_ 中的配置文件，以便传输提供程序可以在错误消息或登录对话框中使用它。 如果提供程序保留此名称，则必须将名称复制到提供程序分配的存储中。 
  
与其他服务提供商紧密结合的传输提供程序可能需要在登录时执行其他工作，以建立配套提供程序之间操作所需的良好凭据。
  
通常，当用户首次登录到配置文件时，将打开传输提供程序。 由于第一次登录配置文件通常先于登录到任何邮件存储，所以 MAPI 后台处理程序通常使用在 _lpulFlags_ 中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用 **TransportLogon。** 稍后，当相应的邮件存储在配置文件会话中可用时，MAPI 后台处理程序将调用 **TransportNotify** 以启动传输提供程序的传入和传出操作。 
  
在  _lpulFlags_ LOGON_NO_CONNECT标志表示传输提供程序的脱机操作。 此标志指示不应进行外部连接;如果传输提供程序在没有外部连接的情况下无法建立会话，则应该返回登录的错误值。 
  
如果传输提供程序设计为使用系统LOGON_SP_IDLE空闲的时间，则传输提供程序应在初始化时在  _lpulFlags_ 中设置该标志。 此类时间通常用于处理自动操作，如自动邮件下载、已设置时间的邮件下载或已设置时间的邮件提交。 如果设置此标志，MAPI 后台处理程序在出现系统空闲时间时调用 **Idle** 以启动此类操作。 MAPI 后台处理程序不会在设置的时间间隔内调用 **Idle;** 相反，它仅在真正的空闲时间内调用。 因此，提供程序不应对调用 **Idle** 方法的频率做出任何假设。 支持空闲时间运算的提供程序应提供其提供程序管理器中的配置属性表。 
  
如果传输提供程序登录成功，提供程序应在  _lppXPLogon_ 参数中返回一个指向登录对象的指针。 MAPI 后台处理程序将使用此对象进行其他提供程序访问。 如果 **TransportLogon** 显示登录对话框，并且用户通常通过单击对话框中的"取消"按钮来取消登录，则提供程序应返回MAPI_E_USER_CANCEL。 
  
对于从 **TransportLogon** 返回的多数错误值，MAPI 将禁用提供程序所属的邮件服务。 MAPI 不会为 MAPI 会话的其余部分调用属于该服务的任何提供程序。 相反，当 **TransportLogon** 从MAPI_E_FAILONEPROVIDER返回错误值时，MAPI 不会禁用提供程序所属的邮件服务。 **TransportLogon** 应MAPI_E_FAILONEPROVIDER如果遇到错误，而该错误不保证为会话的其余部分禁用该服务。 
  
如果提供程序从MAPI_E_UNCONFIGURED返回消息，MAPI 将调用提供程序的邮件服务条目函数，然后重试登录。 MAPI 将MSG_SERVICE_CONFIGURE传递为上下文，为服务提供自行配置的机会。 如果客户端已选择允许在登录时使用用户界面，该服务可以显示其配置属性表以便用户输入配置信息。 
  
如果提供程序发现配置文件中未包含所有必需信息，则它应返回MAPI_E_UNCONFIGURED MAPI 调用提供程序的邮件服务入口点函数。 
  
## <a name="see-also"></a>另请参阅

- [IXPProvider : IUnknown](ixpprovideriunknown.md)  
- [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)  
- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)  
- [IXPLogon::AddressTypes](ixplogon-addresstypes.md)  
- [IXPLogon::Idle](ixplogon-idle.md)  
- [IXPLogon::Poll](ixplogon-poll.md)  
- [IXPLogon::TransportNotify](ixplogon-transportnotify.md) 
- [MAPIERROR](mapierror.md)

