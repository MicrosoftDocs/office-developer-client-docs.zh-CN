---
title: 支持对象概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5b062891-39ab-4334-9706-5b376719d5e4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7f43a50d08daedc623fa1e4570eafa5d58be71f6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577434"
---
# <a name="support-object-overview"></a>支持对象概述

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 提供支持对象，实现的对象[IMAPISupport: IUnknown](imapisupportiunknown.md)界面，在登录时的所有服务提供程序和配置过程的所有邮件服务。 
  
支持对象都无法访问由客户端;它们都是通过 MAPI 实现，调用仅由服务提供商。 Mapispi.h 标头文件中指定的**IMAPISupport**接口。 其标识符 IID_IMAPISup 并且其指针类型 LPMAPISUP。 通过支持对象不公开任何 MAPI 属性。 
  
提供程序，可以指定一个或多个支持对象，具体取决于提供程序的消息服务条目函数调用次数或 MAPI 登录提供程序的次数。 通常情况下，提供程序将登录至少一次每个会话。 每次客户端请求它们的配置文件条目的启动会话登录地址簿和传输提供程序。 每次[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法在客户端调用登录消息存储提供程序。 
  
对于会话中的多个登录，您可以选择是保留和单独使用每个支持对象或保留和使用仅第一个、 放弃每个后续支持对象。 若要保留的支持对象调用其**IUnknown::AddRef**方法。 在您想要保留整个会话支持对象上调用**AddRef**是非常重要;如果未调用 MAPI 释放支持对象和释放其内存。 
  
支持对象的目的是提供相当大数量由提供商提供常用的方法的实现。 每个支持对象还包含特定于自身实例，如会话中，使用提供程序，配置文件一节提供程序正在运行和会话的错误信息的上下文数据。 
  
有四种不同类型的支持对象： 一个用于每个主要的提供程序类型 （通讯簿、 消息存储和传输），另一个用于配置支持。 
  
MAPI 通过包括相关及其所使用的方法的实现自定义每个支持对象。 实现的一些方法，例如[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)，包含在所有支持对象。 实现的其他方法，如[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)，仅适用于特定支持对象。 仅消息存储和传输提供程序可以使用此方法。当通讯簿提供程序或消息服务尝试调用它，MAPI 返回 MAPI_E_NO_SUPPORT。
  
支持对象可用于完成许多任务，如下所示：
  
- 访问配置文件一节。
    
- 复制文件夹或消息。 有关详细信息，请参阅[复制或移动邮件还是一个文件夹](copying-or-moving-a-message-or-a-folder.md)。
    
- 属于其他提供程序的访问对象。 有关详细信息，请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。 
    
- 处理事件通知。 有关详细信息，请参阅[支持的事件通知](supporting-event-notification.md)。
    
- 分配和释放内存。
    
- 获取的唯一标识符。
    
- 使无效对象。
    
- 处理错误。
    
- 注册消息 preprocessors。 
    
- 准备邮件送达报告。 
    
在登录时，MAPI 调用每个服务提供商的提供商对象的登录方法。 对于通讯簿提供程序，MAPI 调用[IABProvider::Logon](iabprovider-logon.md)。 对于消息存储提供程序，MAPI 调用[IMSProvider::Logon](imsprovider-logon.md)。 对于传输提供程序，MAPI 调用[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)。 MAPI 将指针传递到此方法的参数之一中的适当支持对象。 反过来，logon 方法实例化登录对象，将其传递支持对象指针。 如有必要，登录对象将调用支持对象的**IUnknown::AddRef**方法来保留。 有关服务提供商的登录过程的详细信息，请参阅[启动服务提供商](starting-a-service-provider.md)。
  
当客户端注销时，MAPI 调用登录对象的注销方法。 Logoff 方法调用支持对象的**IUnknown::Release**方法，以指示提供程序不再想要呼叫的任何支持方法。 与登录，注销方法有稍微不同的名称。 [IABLogon](iablogoniunknown.md)和[IMSLogon](imslogoniunknown.md)接口具有**注销**方法;[IXPLogon](ixplogoniunknown.md)接口具有[TransportLogoff](ixplogon-transportlogoff.md)方法。 
  
在登录尝试失败，错误 MAPI_E_UNCONFIGURED 或客户端启动配置请求时，会调用消息服务入口点函数。 MAPI 实例化配置支持对象，并为其配置即将更改的提供程序或未配置提供程序调用消息服务入口点函数。 其他支持与对象不同，配置支持对象是有效仅之前的入口点函数返回值;消息服务不调用这些对象的**AddRef**方法保留它们。 
  
通常，MAPI 调用的提供程序的消息服务入口点函数，但有时要求提供程序进行呼叫。 客户端呼叫提供商的[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法，以提示要显示其配置属性表的提供程序时，发生这种。 **留待**应调用[IMAPISupport::GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md)来获得它可以将它们传递给消息服务入口点函数的配置支持对象。 
  
[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法，而无需与 MAPI 链接确定内存分配和释放函数的地址。 使用**GetMemAllocRoutines**还使容易通过周围具有调试代码的分配函数调用跟踪内存泄漏。 如果您调用**GetMemAllocRoutines**，如建议，请执行此操作之前调用[CreateIProp](createiprop.md)函数，这需要分配函数地址作为参数。 
  
当您需要创建新通讯簿或消息存储对象、 创建和其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中设置对象的搜索键。 调用[IMAPISupport::NewUID](imapisupport-newuid.md)获取用于构建搜索关键字的唯一标识符。 不要使用[MAPIUID](mapiuid.md)自己硬编码。 提供程序的**MAPIUID**应仅用于条目标识符。 有关构建搜索关键字的详细信息，请参阅[MAPI 记录和搜索键](mapi-record-and-search-keys.md)。
  
有时，客户端应用程序可以释放对象，而不释放一个或多个其附属对象。 在这种情况下，提供程序可能需要将未发布的对象呈现不可用。 若要执行此操作，提供程序释放的所有资源与对象连接，然后调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)使对象的 vtable 无效。 **MakeInvalid**替换标准 MAPI 实现 vtable **IUnknown**方法 （**QueryInterface**、 **AddRef**和**发行版**），并使所有其他方法可返回 MAPI_E_INVALID_OBJECT。 **MakeInvalid**还释放 vtable 之外的所有对象的内存。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

