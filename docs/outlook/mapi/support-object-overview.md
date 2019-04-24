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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327165"
---
# <a name="support-object-overview"></a>支持对象概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供在配置期间, 在登录过程中和所有邮件服务的所有服务提供程序的支持对象 (一个实现[IMAPISupport: IUnknown](imapisupportiunknown.md)接口的对象)。 
  
客户端无法访问支持对象;它们由 MAPI 实现, 并且仅由服务提供程序调用。 **IMAPISupport**接口是在 Mapispi 头文件中指定的。 其标识符为 IID_IMAPISup, 其指针类型为 LPMAPISUP。 支持对象未公开任何 MAPI 属性。 
  
可以为提供程序提供一个或多个支持对象, 具体取决于 MAPI 在其上记录提供程序的次数或调用提供程序的邮件服务条目函数的次数。 通常情况下, 提供程序每次会话至少会登录一次。 每次客户端启动带有请求的配置文件条目的会话时, 都会记录通讯簿和传输提供程序。 每次客户端调用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法时, 都会记录邮件存储提供程序。 
  
在会话中有多个登录的情况下, 您可以选择单独保留和使用每个支持对象, 也可以保留并仅使用第一个, 以丢弃每个后续的支持对象。 若要保留支持对象, 请调用其**IUnknown:: AddRef**方法。 对要在会话中保留的支持对象调用**AddRef**极其重要;如果未进行呼叫, MAPI 将释放支持对象并释放其内存。 
  
支持对象的目的是为提供程序通常使用的大量方法提供实现。 每个支持对象还包含特定于其自己的实例的上下文数据, 如提供程序正在运行的会话、提供程序所使用的配置文件部分以及会话的错误消息。 
  
有四种不同类型的支持对象: 每个主要提供程序类型 (通讯簿、邮件存储和传输), 一个用于配置支持。 
  
MAPI 通过包括与其使用相关的方法的实现来自定义每个支持对象。 某些方法的实现 (如[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)) 包含在所有支持对象中。 其他方法 (如[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)) 的实现仅适用于特定的支持对象。 只有邮件存储和传输提供程序可以使用此方法;当通讯簿提供程序或邮件服务尝试呼叫它时, MAPI 将返回 MAPI_E_NO_SUPPORT。
  
支持对象可用于完成以下多项任务:
  
- 访问配置文件部分。
    
- 复制文件夹或邮件。 有关详细信息, 请参阅[复制或移动邮件或文件夹](copying-or-moving-a-message-or-a-folder.md)。
    
- 访问属于其他提供程序的对象。 有关详细信息, 请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。 
    
- 处理事件通知。 有关详细信息, 请参阅[支持事件通知](supporting-event-notification.md)。
    
- 分配和释放内存。
    
- 获取唯一标识符。
    
- 使对象失效。
    
- 处理错误。
    
- 注册邮件 preprocessors。 
    
- 准备邮件传递报告。 
    
在登录时, MAPI 会调用每个服务提供程序的提供程序对象的登录方法。 对于通讯簿提供程序, MAPI 调用[IABProvider:: Logon](iabprovider-logon.md)。 对于邮件存储区提供程序, MAPI 调用[IMSProvider:: Logon](imsprovider-logon.md)。 对于传输提供程序, MAPI 调用[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)。 MAPI 将指向此方法的其中一个参数中相应的支持对象的指针传递给该方法。 登录方法反过来实例化一个登录对象, 并将其传递给支持对象指针。 如果必要, 登录对象将调用支持对象的**IUnknown:: AddRef**方法来保留它。 有关服务提供程序的登录过程的详细信息, 请参阅[启动服务提供程序](starting-a-service-provider.md)。
  
当客户端注销时, MAPI 将调用该登录对象的注销方法。 注销方法调用支持对象的**IUnknown:: Release**方法, 以指示提供程序不再打算调用任何支持方法。 与登录一样, 注销方法的名称略有不同。 [IABLogon](iablogoniunknown.md)和[IMSLogon](imslogoniunknown.md)接口具有**注销**方法;[IXPLogon](ixplogoniunknown.md)接口具有[TransportLogoff](ixplogon-transportlogoff.md)方法。 
  
当登录尝试失败并出现错误 MAPI_E_UNCONFIGURED 或客户端启动配置请求时, 将调用邮件服务入口点函数。 MAPI 实例化配置支持对象, 并调用其配置即将更改的未配置的提供程序或提供程序的邮件服务入口点函数。 与其他支持对象不同的是, 配置支持对象仅在入口点函数返回时才有效;邮件服务不会调用这些对象的**AddRef**方法来保留它们。 
  
通常情况下, MAPI 会调用提供程序的邮件服务入口点函数, 但有时会要求提供程序发出呼叫。 当客户端调用提供程序的[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法以提示提供程序显示其配置属性表时, 可能会发生这种情况。 **SettingsDialog**应调用[IMAPISupport:: GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md)获取可传递给邮件服务入口点函数的配置支持对象。 
  
[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法可用于确定内存分配和未分配函数的地址, 而无需使用 MAPI 进行链接。 通过使用**GetMemAllocRoutines** , 还可以更轻松地通过使用调试代码来处理分配函数调用来跟踪内存泄漏。 如果调用**GetMemAllocRoutines**, 则在调用[CreateIProp](createiprop.md)函数之前, 请先执行此操作, 这需要将分配函数作为参数进行寻址。 
  
当您需要创建新的通讯簿或邮件存储对象时, 请在其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中创建并设置该对象的搜索关键字。 调用[IMAPISupport:: NewUID](imapisupport-newuid.md)以获取用于生成搜索密钥的唯一标识符。 请勿使用您自己的硬编码[MAPIUID](mapiuid.md)。 提供程序的**MAPIUID**仅用于条目标识符。 有关构建搜索关键字的详细信息, 请参阅[MAPI 记录和搜索关键字](mapi-record-and-search-keys.md)。
  
有时, 客户端应用程序可以释放对象, 而无需释放它的一个或多个关联对象。 在这种情况下, 提供程序可能需要呈现一个 unreleased 对象不可用。 若要执行此操作, 提供程序将释放与该对象连接的所有资源, 然后调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md)使该对象的 vtable 无效。 **MakeInvalid**将 vtable 的**IUnknown**方法 (**QueryInterface**、 **AddRef**和**Release**) 替换为标准 MAPI 实现, 并导致所有其他方法返回 MAPI_E_INVALID_OBJECT。 **MakeInvalid**还释放除 vtable 之外的所有对象的内存。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

