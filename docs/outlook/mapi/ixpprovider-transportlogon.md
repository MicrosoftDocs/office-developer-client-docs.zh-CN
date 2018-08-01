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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 01a8e3c479ab3ddd1be9386e033b993fda5835a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776177"
---
# <a name="ixpprovidertransportlogon"></a>IXPProvider::TransportLogon

**适用于**： Outlook 
  
建立一个会话中的客户端应用程序登录到传输提供程序。 
  
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

_lpMAPISup_: [in] 此指针指向此会话的 MAPI 的回调函数的传输提供程序的支持对象。 此对象保持有效，直到传输提供程序将其发布。
    
_ulUIParam_: [in] 任何对话框的父窗口或该方法显示的窗口句柄。 _UlUIParam_参数可以是非空，例如当 LOGON_SETUP 标记_lpulFlags_参数中设置。 
    
_lpszProfileName_: [in] 此指针指向用户的配置文件名称。 主要时必须显示一个对话框，才能使用_lpszProfileName_参数。 
    
_lpulFlags_: [中，out] 控制如何建立登录会话的标志位掩码。 通过 MAPI 后台处理程序，可以输入上设置以下标志：
    
  - LOGON_NO_CONNECT： 的用户帐户登录到此传输提供程序之外的传输和接收的消息的目的。 传输提供程序不应尝试进行任何连接到其他邮件系统。
        
  - LOGON_NO_DIALOG： 应不显示任何对话框，即使当前已保存的用户凭据无效或不足进行登录。
        
  - LOGON_NO_INBOUND： 传输提供程序没有初始化接收的消息，并且不应接受传入消息。 MAPI 后台处理程序可用于[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法更高版本信号传输提供程序来启用传入邮件处理。 
        
  - LOGON_NO_OUTBOUND： 传输提供程序没有初始化发送邮件，如 MAPI 后台处理程序不提供任何。 如果客户端应用程序需要期间一条消息构成的连接到远程提供程序，以便它可以进行[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法调用，传输提供程序应进行连接。 MAPI 后台处理程序可以使用**TransportNotify**时传出操作可以开始信号传输提供程序。 
      
  - MAPI_UNICODE： 配置文件名称的传入的字符串采用 Unicode 格式。 如果 MAPI\_未设置 UNICODE 标志、 字符串是 ANSI 格式。
      
    以下标志可以由传输提供程序设置输出：
      
  - LOGON_SP_IDLE: MAPI 后台处理程序经常空闲时间处理的呼叫传输提供程序的[IXPLogon::Idle](ixplogon-idle.md)方法请求。 
      
  - MAPI 后台处理程序经常[IXPLogon::Poll](ixplogon-poll.md)对对象调用方法返回的登录检查新邮件的 LOGON_SP_POLL： 请求。 如果未设置此标志，MAPI 后台处理程序只检查新邮件时传输提供程序将使用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法来通知后台处理程序要处理的新邮件。 传输提供程序有效地将成为仅发送通过不设置此标志并不通知邮件回执 MAPI 后台处理程序。 
      
  - LOGON_SP_RESOLVE: MAPI 后台处理程序解析为的请求完全本传输提供程序不支持所有收件人的邮件地址的地址。 因此传输提供程序，可以构造的所有收件人的答复路径。
      
  - MAPI_UNICODE： 返回的字符串在[MAPIERROR](mapierror.md)结构中，如果有，采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
_lppMAPIError_: [输出] 指向返回**MAPIERROR**结构的指针的指针，如果有，包含用于错误的版本、 组件及上下文信息。 如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。 
    
_lppXPLogon_: [输出] 指向返回的传输提供程序登录对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK： 呼叫成功或多个预期值返回。
    
MAPI_E_FAILONEPROVIDER： 此提供程序不能登录，但不是服务应禁用此错误。 
    
MAPI_E_UNCONFIGURED: 配置文件不包含为登录完成足够的信息。 MAPI 调用的提供程序的消息服务入口点函数。
    
MAPI_E_UNKNOWN_CPID： 提供程序无法支持客户端的代码页。
    
MAPI_E_UNKNOWN_LCID： 提供程序无法支持客户端的区域设置信息。
    
MAPI_E_USER_CANCEL: 用户已取消该操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用**IXPProvider::TransportLogon**方法建立登录会话的用户。 
  
大多数传输提供程序使用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法提供指向用于保存和检索用户标识信息、 服务器地址和凭据_lpMAPISup_参数的支持对象。 通过使用**OpenProfileSection**，传输提供程序可以保存任意信息并将其与登录到特定的资源关联。 例如，提供程序可以使用**OpenProfileSection**保存的帐户名和密码与特定会话和任何服务器的名称或其他必要的信息，该会话所需访问的资源关联。 MAPI 隐藏信息与从外部访问的资源关联。 可通过_lpMAPISup_配置文件部分管理 MAPI 后台打印程序以便与此用户上下文相关的数据分开的其他上下文数据。 
  
传输提供程序必须支持对象上调用**IUnknown::AddRef**方法，并对该对象保留一份指针，提供登录对象的一部分。 
  
以便传输提供程序可以使用它在错误消息或登录对话框提供_lpszProfileName_的配置文件显示名称。 如果提供程序保留此名称，必须将它复制到存储分配服务提供商。 
  
与其他服务提供程序紧密耦合的传输提供程序可能需要执行其他工作登录建立助理提供程序之间的操作所需的良好凭据。
  
通常，当用户首次登录到配置文件打开传输提供程序。 由于首次登录到配置文件因此通常位于之前登录到任何消息存储库，MAPI 后台处理程序通常与_lpulFlags_中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用**TransportLogon** 。 更高版本，可用于配置文件会话的相应的消息存储后，MAPI 后台处理程序调用**TransportNotify**启动传输提供程序的传入和传出操作。 
  
传递中_lpulFlags_信号的 LOGON_NO_CONNECT 标志脱机操作的传输提供程序。 此标志指示应将没有外部连接;如果传输提供程序无法建立一个会话外部连接的情况下，则应返回错误值进行登录。 
  
传输提供程序应中设置了 LOGON_SP_IDLE 标志_lpulFlags_在初始化时如果它旨在使用否则为系统等待的时间空闲。 此类时常用来处理自动操作，如自动邮件下载，超时消息下载，或超时消息提交。 如果设置此标志，系统空闲时间发生启动这些操作时，MAPI 后台处理程序调用**空闲**。 MAPI 后台处理程序以设置的间隔; 不调用**空闲**相反，它仅在过程中调用，则返回 true 的空闲时间。 因此，将调用其**空闲**方法的频率任何假设不应处理提供程序。 提供程序支持空闲时间操作应为其提供其提供程序的属性表中的配置用户界面。 
  
如果成功传输提供程序登录，提供程序应返回_lppXPLogon_参数中的指针对登录对象。 MAPI 后台处理程序将使用其他提供程序访问此对象。 如果**TransportLogon**显示一个登录对话框，用户取消登录通常通过单击对话框中的**取消**按钮提供程序应返回 MAPI_E_USER_CANCEL。 
  
对于大多数**TransportLogon**从返回的错误值，MAPI 禁用提供程序所属的消息服务。 MAPI 将不会调用属于该 MAPI 会话的 rest 服务的任何提供程序。 相比之下，当**TransportLogon**返回 MAPI_E_FAILONEPROVIDER 错误值从其登录时，MAPI 不禁用邮件服务提供程序所属。 如果遇到错误，不保证禁用会话的 rest 服务， **TransportLogon**应返回 MAPI_E_FAILONEPROVIDER。 
  
如果提供程序返回 MAPI_E_UNCONFIGURED 从其登录，MAPI 将调用提供程序的消息服务条目函数，然后重试登录。 MAPI 将作为上下文，以使该服务配置本身有机会传递 MSG_SERVICE_CONFIGURE。 如果客户端已经选择允许在登录的用户界面，该服务可以将其配置属性表，，以便用户可以输入配置信息。 
  
如果提供程序查找所有所需的信息不在配置文件中，则应返回 MAPI_E_UNCONFIGURED，以便 MAPI 调用的提供程序的消息服务入口点函数。 
  
## <a name="see-also"></a>另请参阅

- [IXPProvider : IUnknown](ixpprovideriunknown.md)  
- [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)  
- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)  
- [IXPLogon::AddressTypes](ixplogon-addresstypes.md)  
- [IXPLogon::Idle](ixplogon-idle.md)  
- [IXPLogon::Poll](ixplogon-poll.md)  
- [IXPLogon::TransportNotify](ixplogon-transportnotify.md) 
- [MAPIERROR](mapierror.md)

