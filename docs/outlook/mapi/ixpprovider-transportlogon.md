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
  
建立一个会话, 客户端应用程序在该会话中登录到传输提供程序。 
  
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

_lpMAPISup_: [in] 指向针对此会话的 MAPI 中的回调函数的传输提供程序的支持对象的指针。 在传输提供程序释放此对象之前, 此对象一直保持有效。
    
_ulUIParam_: [in] 处理此方法显示的任何对话框或窗口的父窗口。 _ulUIParam_参数可以为非 null, 例如, 在_lpulFlags_参数中设置 LOGON_SETUP 标志时。 
    
_lpszProfileName_: [in] 指针指向用户的配置文件名称。 _lpszProfileName_参数主要在必须显示对话框时使用。 
    
_lpulFlags_: [in, out] 用于控制如何建立登录会话的标志的位掩码。 MAPI 后台处理程序可对输入设置以下标志:
    
  - LOGON_NO_CONNECT: 用户帐户出于邮件传输和接收之外的目的登录到此传输提供程序。 传输提供程序不应尝试对其他邮件系统进行任何连接。
        
  - LOGON_NO_DIALOG: 即使当前保存的用户凭据无效或不足以登录, 也不应显示任何对话框。
        
  - LOGON_NO_INBOUND: 传输提供程序无需为接收邮件进行初始化, 也不应接受传入的邮件。 MAPI 后台处理程序可以稍后使用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法向传输提供程序发出信号, 以启用传入邮件处理。 
        
  - LOGON_NO_OUTBOUND: 传输提供程序无需对发送邮件进行初始化, 因为 MAPI 后台处理程序不会提供任何。 如果客户端应用程序要求在消息的撰写过程中连接到远程提供程序, 以便它可以发出[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法调用, 则传输提供程序应进行连接。 MAPI 后台处理程序可以使用**TransportNotify**在传出操作开始时向传输提供程序发出信号。 
      
  - MAPI_UNICODE: 配置文件名称的传入字符串采用 UNICODE 格式。 如果未设置\_MAPI UNICODE 标志, 则字符串将采用 ANSI 格式。
      
    传输提供程序可对输出设置以下标志:
      
  - LOGON_SP_IDLE: 请求 MAPI 后台处理程序频繁调用传输提供程序的[IXPLogon::](ixplogon-idle.md) idle-time 处理的空闲方法。 
      
  - LOGON_SP_POLL: 请求 MAPI 后台处理程序经常对返回的登录对象调用[IXPLogon::P oll](ixplogon-poll.md)方法, 以检查是否有新邮件。 如果未设置此标志, 则 MAPI 后台处理程序仅在传输提供程序使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法时检查新邮件, 以通知后台打印程序有要处理的新邮件。 通过不设置此标志, 传输提供程序将有效地变为仅发送, 而不会通知邮件接收的 MAPI 后台处理程序。 
      
  - LOGON_SP_RESOLVE: 请求 MAPI 后台处理程序解析为完整地址此传输提供程序不支持的所有收件人的邮件地址。 因此, 传输提供程序可以为所有收件人构造答复路径。
      
  - MAPI_UNICODE: [MAPIERROR](mapierror.md)结构中返回的字符串 (如果有) 采用 UNICODE 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
_lppMAPIError_: [out] 指向指向返回的**MAPIERROR**结构的指针的指针 (如果有), 其中包含错误的版本、组件和上下文信息。 如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
_lppXPLogon_: [out] 指向返回的传输提供程序登录对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK: 调用成功, 并返回了所需的值。
    
MAPI_E_FAILONEPROVIDER: 此提供程序无法登录, 但此错误不应禁用该服务。 
    
MAPI_E_UNCONFIGURED: 配置文件不包含足够的信息, 无法完成登录。 MAPI 调用提供程序的邮件服务入口点函数。
    
MAPI_E_UNKNOWN_CPID: 提供程序无法支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID: 提供程序无法支持客户端的区域设置信息。
    
MAPI_E_USER_CANCEL: 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用**IXPProvider:: TransportLogon**方法为用户建立登录会话。 
  
大多数传输提供程序使用由_lpMAPISup_参数指向的支持对象所提供的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法, 以保存和检索用户标识信息、服务器地址和凭据。 通过使用**OpenProfileSection**, 传输提供程序可以保存任意信息, 并将其与登录到特定资源相关联。 例如, 提供程序可以使用**OpenProfileSection**保存与特定会话相关联的帐户名称和密码, 以及访问该会话的资源所需的任何服务器名称或其他必要信息。 MAPI 在外部访问中隐藏与资源相关联的信息。 通过_lpMAPISup_提供的配置文件节由 MAPI 后台处理程序进行管理, 因此与此用户上下文相关的数据与其他上下文的数据分开。 
  
传输提供程序必须调用支持对象上的**IUnknown:: AddRef**方法, 并将指针的副本作为提供程序登录对象的一部分保留给此对象。 
  
提供_lpszProfileName_中的配置文件显示名称, 以便传输提供程序可以在错误消息或登录对话框中使用它。 如果提供程序保留此名称, 则必须将其复制到提供程序分配的存储中。 
  
与其他服务提供程序紧密结合的传输提供程序可能必须在登录时执行额外的工作, 才能建立配套提供程序之间的操作所需的正确凭据。
  
通常情况下, 当用户首次登录到配置文件时, 将打开传输提供程序。 由于第一次登录到配置文件时通常会登录到任何邮件存储, 因此 MAPI 后台处理程序通常会同时在_lpulFlags_中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用**TransportLogon** 。 之后, 在配置文件会话中提供相应的邮件存储区时, MAPI 后台处理程序将调用**TransportNotify**以启动传输提供程序的传入和传出操作。 
  
在_lpulFlags_中传递 LOGON_NO_CONNECT 标志以通知传输提供程序的脱机操作。 此标志指示不应进行外部连接;如果传输提供程序无法在没有外部连接的情况下建立会话, 它应返回登录的错误值。 
  
如果在_lpulFlags_中, 传输提供程序应在初始化时设置 LOGON_SP_IDLE 标志, 如果它设计为使用系统本来会处于空闲状态的时间。 此类时间通常用于处理自动操作, 例如自动邮件下载、计时邮件下载或定时邮件提交。 如果设置了此标志, 则 MAPI 后台处理程序会在系统空闲时间启动此类操作时呼叫**空闲**。 MAPI 后台处理程序不会在设置的时间间隔内呼叫**空闲**;而只是在真正的空闲时间内调用。 因此, 提供程序不应针对其**空闲**方法的调用频率的任何假设进行操作。 支持空闲时间操作的提供程序应在其提供程序属性表中为其提供配置用户界面。 
  
如果传输提供程序登录成功, 则提供程序应在_lppXPLogon_参数中返回一个指向登录对象的指针。 MAPI 后台处理程序将使用此对象以获取其他提供程序访问权限。 如果**TransportLogon**显示登录对话框, 并且用户通过单击对话框中的 "取消" 按钮 (该对话框中的 "**取消**" 按钮) 来取消登录, 则提供程序应返回 MAPI_E_USER_CANCEL。 
  
对于从**TransportLogon**返回的大多数错误值, MAPI 将禁用该提供程序所属的邮件服务。 mapi 将不会为 mapi 会话的其余部分调用任何属于该服务的提供程序。 相比之下, 当**TransportLogon**从其登录中返回 MAPI_E_FAILONEPROVIDER 错误值时, MAPI 不会禁用该提供程序所属的邮件服务。 如果遇到不保证在会话的其余部分禁用服务的错误, **TransportLogon**应返回 MAPI_E_FAILONEPROVIDER。 
  
如果提供程序从其登录返回 MAPI_E_UNCONFIGURED, 则 MAPI 将调用提供程序的邮件服务条目功能, 然后重试该登录。 MAPI 将 MSG_SERVICE_CONFIGURE 作为上下文进行传递, 使服务有机会对自身进行配置。 如果客户端已选择允许登录时使用用户界面, 则服务可以显示其配置属性表, 以便用户可以输入配置信息。 
  
如果提供程序发现所有必需的信息都不在配置文件中, 则应返回 MAPI_E_UNCONFIGURED, 以便 MAPI 调用提供程序的邮件服务入口点函数。 
  
## <a name="see-also"></a>另请参阅

- [IXPProvider : IUnknown](ixpprovideriunknown.md)  
- [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)  
- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)  
- [IXPLogon::AddressTypes](ixplogon-addresstypes.md)  
- [IXPLogon::Idle](ixplogon-idle.md)  
- [IXPLogon::Poll](ixplogon-poll.md)  
- [IXPLogon::TransportNotify](ixplogon-transportnotify.md) 
- [MAPIERROR](mapierror.md)

