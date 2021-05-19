---
title: 支持对象概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5b062891-39ab-4334-9706-5b376719d5e4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 55d8a9c78ae5132eaa8cf0f0aec5b252ef83b926
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433610"
---
# <a name="support-object-overview"></a>支持对象概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 为登录期间的所有服务提供商以及配置期间的所有邮件服务提供支持对象（一个实现 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 接口的对象）。 
  
客户端无法访问支持对象;它们由 MAPI 实现，并且仅由服务提供商调用。 **IMAPISupport** 接口在 Mapispi.h 头文件中指定。 它的标识符IID_IMAPISup指针类型是 LPMAPISUP。 支持对象不会公开任何 MAPI 属性。 
  
提供程序可以有一个或多个支持对象，具体取决于 MAPI 记录提供程序的时间或调用提供程序的邮件服务条目函数次数。 通常，提供程序将至少每个会话登录一次。 每当客户端使用请求其的配置文件条目启动会话时，通讯簿和传输提供程序都会登录。 每次客户端调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 方法时，都会登录消息存储提供程序。 
  
在会话中多次登场的情况下，可以选择单独保留和使用每个支持对象，也可以选择仅保留并使用第一个，丢弃每个后续支持对象。 若要保留支持对象，请调用其 **IUnknown：：AddRef** 方法。 对要在整个会话中保留的支持对象调用 **AddRef** 非常重要;如果未进行调用，MAPI 将释放支持对象并释放其内存。 
  
支持对象的目的是为提供程序常用的大量方法提供实现。 每个支持对象还包含特定于其自己的实例的上下文数据，例如提供程序运行的会话、提供程序使用的配置文件部分以及会话的错误信息。 
  
支持对象有四种不同类型的：一种用于每个主要提供程序类型 (通讯簿、邮件存储和传输) 一种用于配置支持。 
  
MAPI 通过包括与它的用法相关的方法实现来自定义每个支持对象。 某些方法（如 [IMAPISupport：：OpenProfileSection）](imapisupport-openprofilesection.md)的实现包含在所有支持对象中。 其他方法（如 [IMAPISupport：：SpoolerNotify）](imapisupport-spoolernotify.md)的实现仅适用于特定支持对象。 只有邮件存储和传输提供程序才能使用此方法;当通讯簿提供程序或邮件服务尝试调用它时，MAPI 将返回 MAPI_E_NO_SUPPORT。
  
支持对象可用于完成许多任务，例如：
  
- 访问配置文件部分。
    
- 复制文件夹或邮件。 有关详细信息，请参阅复制 [或移动邮件或文件夹](copying-or-moving-a-message-or-a-folder.md)。
    
- 访问属于其他提供程序的对象。 有关详细信息，请参阅支持 [对象访问和比较](supporting-object-access-and-comparison.md)。 
    
- 处理事件通知。 有关详细信息，请参阅支持 [事件通知](supporting-event-notification.md)。
    
- 分配和释放内存。
    
- 获取唯一标识符。
    
- 使对象无效。
    
- 处理错误。
    
- 注册邮件预处理器。 
    
- 准备邮件送达报告。 
    
在登录时，MAPI 调用每个服务提供商的提供程序对象的登录方法。 对于通讯簿提供程序，MAPI 调用 [IABProvider：：Logon](iabprovider-logon.md)。 对于邮件存储提供程序，MAPI 调用 [IMSProvider：：Logon](imsprovider-logon.md)。 对于传输提供程序，MAPI 调用 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)。 MAPI 将指向此方法的参数之一中的相应支持对象的指针传递。 登录方法反过来实例化登录对象，并传递支持对象指针。 登录对象调用支持对象的 **IUnknown：：AddRef** 方法来保留它（如有必要）。 有关服务提供商的登录过程详细信息，请参阅启动 [服务提供程序](starting-a-service-provider.md)。
  
客户端注销后，MAPI 将调用登录对象的 logoff 方法。 logoff 方法调用支持对象的 **IUnknown：：Release** 方法，以指示提供程序不再打算调用任何支持方法。 与登录一样，注销方法的名称略有不同。 [IABLogon 和](iablogoniunknown.md) [IMSLogon](imslogoniunknown.md)接口具有 **Logoff** 方法;[IXPLogon](ixplogoniunknown.md)接口具有 [TransportLogoff](ixplogon-transportlogoff.md)方法。 
  
当登录尝试失败，出现错误或客户端启动配置MAPI_E_UNCONFIGURED调用消息服务入口点函数。 MAPI 实例化配置支持对象，并调用未配置提供程序或其配置即将更改的提供程序的消息服务入口点函数。 与其他支持对象不同，配置支持对象仅在入口点函数返回之前有效;邮件服务不调用这些对象的 **AddRef** 方法来保留它们。 
  
通常，MAPI 调用提供程序的邮件服务入口点功能，但有时会要求提供程序进行调用。 当客户端调用提供程序的 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法以提示提供程序显示其配置时，属性表。 **SettingsDialog** 应调用 [IMAPISupport：：GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md) 以获取可以传递给邮件服务入口点函数的配置支持对象。 
  
[IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法可用于确定内存分配和释放函数的地址，而无需与 MAPI 链接。 通过使用 **GetMemAllocRoutines，** 通过使用调试代码围绕分配函数调用来更轻松地跟踪内存泄漏。 如果按照建议调用 **GetMemAllocRoutines**，则先调用 [CreateIProp](createiprop.md) 函数，这需要分配函数地址作为参数。 
  
当需要创建新的通讯簿或邮件存储对象时，请在其 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中为该对象创建和设置搜索密钥。 调用 [IMAPISupport：：NewUID](imapisupport-newuid.md) 以获取用于生成搜索密钥的唯一标识符。 请勿使用自己的硬编码 [MAPIUID](mapiuid.md)。 提供程序的 **MAPIUID** 应仅用于条目标识符。 有关构造搜索键的信息，请参阅[MAPI Record and Search Keys。](mapi-record-and-search-keys.md)
  
客户端应用程序有时可以释放对象，而不会释放其一个或多个附属对象。 在这种情况下，提供程序可能需要呈现一个不可用的未响应对象。 为此，提供程序将释放与对象连接的所有资源，然后调用 [IMAPISupport：：MakeInvalid](imapisupport-makeinvalid.md) 使对象的 vtable 无效。 **MakeInvalid** 将 vtable 的 **IUnknown** 方法 (**QueryInterface、AddRef** 和 **Release**) 替换为标准 MAPI 实现，并会导致所有其他方法返回 MAPI_E_INVALID_OBJECT。  **MakeInvalid** 还释放除 vtable 对象外的所有对象内存。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

