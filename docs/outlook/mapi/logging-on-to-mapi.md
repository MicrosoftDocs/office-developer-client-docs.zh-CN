---
title: 登录 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 05bafe43-a78a-4659-92f0-0b4fe444c64f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cce43301ac73a5646e263b2ab92700e57804637d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419707"
---
# <a name="logging-on-to-mapi"></a>登录 MAPI
 
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通过调用**MAPILogonEx**函数登录到 MAPI 子系统。 有关详细信息, 请参阅[MAPILogonEx](mapilogonex.md)。 **MAPILogonEx**验证配置文件中的配置文件选择和配置, 以及配置文件中的每个服务提供程序。 配置完成后, MAPI 会先启动通讯簿提供程序, 然后才能启动邮件存储提供程序。 传输提供程序在其服务首次需要时启动。 
  
## <a name="choose-a-profile"></a>选择配置文件
  
- 将表示_lpszProfileName_参数中的配置文件名称的字符串传递给**MAPILogonEx**, 或 .。。
    
- 允许用户通过在_lpszProfileName_参数中传递 NULL 并设置 MAPI_LOGON_UI 标志来指定配置文件, 或者 .。。 

- 通过在_lpszProfileName_参数中传递 NULL 并设置 MAPI_USE_DEFAULT 标志来选择默认配置文件。 
    
如果需要特定的配置文件, 而不是默认配置文件, 则必须将其名称保存在自己的配置数据库中, 或使用特定的命名约定。 MAPI 不公开配置文件表中的名称和默认标志之外的任何配置文件属性, 并且为邮件客户端和相关的 IPM 应用程序保留默认的配置文件标志。
  
向**MAPILogonEx**提供部分配置文件或提供程序配置信息的客户端必须通过允许显示对话框来提示用户输入其他数据。 如果缺少信息, 并且**MAPILogonEx**无法提示用户提供此信息, 则登录将失败。 不需要用户输入的客户端可以禁止显示对话框。 
  
**MAPILogonEx**用于启用用户界面的标志是相互排斥的;只能设置一个。 将这些标志保留为未设置将禁止显示用户界面, 从而导致**MAPILogonEx**在必要信息丢失时失败。 也就是说, 如果您禁用用户界面并为_lpszProfileName_参数传递 NULL, 而不设置 MAPI_USE_DEFAULT 标志, 则**MAPILogonEx**将失败, 因为它无法检索配置文件名称。 
  
**MAPILogonEx**建立的会话可以是单个邮件会话、共享邮件会话或 nonmessaging 会话。 单个邮件传递会话是客户端和 MAPI 子系统之间的专用连接, 可以通过在对**MAPILogonEx**的调用中设置 MAPI_NEW_SESSION 标志建立。
  
共享邮件会话是多个邮件客户端可以使用的连接。 通常为客户端建立共享会话, 以使用相同的配置文件。 若要将新会话建立为共享会话, 请设置 MAPI_ALLOW_OTHERS 标志。 
  
## <a name="use-an-existing-shared-session"></a>使用现有共享会话
  
- 请勿设置 MAPI_NEW_SESSION 标志。
    
- 请勿设置 MAPI_ALLOW_OTHERS 标志。
    
- 为_lpszProfileName_参数传递 NULL。 
    
- 为_lpszPassword_参数传递 NULL。 
    
Nonmessaging 会话允许客户端访问 MAPI 子系统, 但不允许发送或接收邮件。 配置或管理应用程序是可能需要建立 nonmessaging 会话的客户端示例。 若要请求 nonmessaging 会话, 请设置 MAPI_NO_MAIL 标志。 设置此标志将在不通知 MAPI 后台处理程序的情况下记录客户端。 使用此标志登录到 MAPI 的客户端可能会收到已读状态报告。
  
应仅设置 MAPI_NO_MAIL 标志:
  
- 如果客户端在会话过程中不会发送或接收邮件。
    
- 如果您的客户端具有对配置文件内容的完全控制, 并且将使用紧密耦合的邮件存储和传输提供程序 (如 Microsoft Exchange 提供程序) 发送和接收邮件。
    
邮件客户端可以与 nonmessaging 客户端共享会话。 共享会话的一个成员的特征不受其他成员特征的影响。 也就是说, 如果您使用 MAPI_NO_MAIL 和 MAPI_ALLOW_OTHERS 标志集登录, 则登录到会话的邮件客户端不会对客户端的操作产生影响, 反之亦然。 邮件客户端将仍能发送和接收邮件, 而您的客户端将不能。
  
**MAPILogonEx**定义了您可以设置的其他一些标志: 
  
- MAPI_FORCE_DOWNLOAD 表示应在**MAPILogonEx**返回之前下载传入的邮件。 如果不设置此标志, 则稍后会在后台下载邮件。 
    
- MAPI_SERVICE_UI_ALWAYS 请求配置文件中的每个邮件服务显示一个 "配置" 对话框。
    
- MAPI_NT_SERVICE 指示您的客户端作为 Windows 服务实现。 如果客户端是服务, 则必须设置此标志。
    
每次成功登录后, **MAPILogonEx**将返回指向 MAPI 会话的指针。 您可以使用此指针调用**IMAPISession**接口的方法。 有关详细信息, 请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。 会话指针 (无论会话的类型如何) 对于接收它们的客户端是唯一的, 并且在任务之间是无效的。
  

