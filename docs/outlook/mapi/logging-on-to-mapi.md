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
  
客户端应用程序通过调用 **MAPILogonEx** 函数登录到 MAPI 子系统。 有关详细信息，请参阅 [MAPILogonEx](mapilogonex.md)。 **MAPILogonEx** 验证配置文件中每个服务提供商的配置文件选择和配置。 配置后，MAPI 在启动邮件存储提供程序之前启动通讯簿提供程序。 传输提供程序在首次需要其服务时启动。 
  
## <a name="choose-a-profile"></a>选择配置文件
  
- 将表示  _lpszProfileName_ 参数中的配置文件名称的字符串传递到 **MAPILogonEx** 或...
    
- 允许用户指定配置文件，具体方法为在  _lpszProfileName_ 参数中传递 NULL，并设置MAPI_LOGON_UI或... 

- 选择默认配置文件，方法为在  _lpszProfileName_ 参数中传递 NULL 并设置MAPI_USE_DEFAULT标记。 
    
如果需要除默认配置文件外的特定配置文件，则必须将其名称保存在自己的配置数据库中或使用特定的命名约定。 MAPI 不会公开配置文件表中除名称和默认标志外的任何配置文件属性，并且默认配置文件标记保留用于邮件客户端和相关 IPM 应用程序。
  
向 **MAPILogonEx** 提供部分配置文件或提供程序配置信息的客户端必须通过允许显示对话框来提示用户输入其他数据。 如果信息缺失且 **MAPILogonEx** 无法提示用户提供该信息，则登录将失败。 不需要用户输入的客户端可以禁止对话框显示。 
  
**MAPILogonEx** 用于启用用户界面的标志是互斥的;只能设置一个。 取消设置这些标志将禁止显示用户界面，从而导致 **MAPILogonEx** 在缺少必要信息时失败。 也就是说，如果禁用用户界面，并传递  _lpszProfileName_ 参数的 NULL，并且未设置 MAPI_USE_DEFAULT 标志 **，MAPILogonEx** 将失败，因为它无法检索配置文件名称。 
  
**MAPILogonEx** 建立会话可以是单个消息会话、共享消息会话或非邮件会话。 单个消息会话是客户端与 MAPI 子系统之间的专用连接，可以通过在 **MAPILogonEx** 调用中设置 MAPI_NEW_SESSION 标志来建立。
  
共享消息会话是多个邮件客户端可以使用的连接。 通常，为使用相同配置文件的客户端建立共享会话。 若要将新会话建立为共享会话，请设置MAPI_ALLOW_OTHERS标记。 
  
## <a name="use-an-existing-shared-session"></a>使用现有共享会话
  
- 不要设置MAPI_NEW_SESSION标志。
    
- 不要设置MAPI_ALLOW_OTHERS标志。
    
- 为  _lpszProfileName 参数传递_ NULL。 
    
- 为  _lpszPassword_ 参数传递 NULL。 
    
非messaging会话允许客户端访问 MAPI 子系统，但不允许发送或接收消息。 配置或管理应用程序是可能需要建立非messaging会话的客户端示例。 若要请求非messaging会话，请设置MAPI_NO_MAIL标记。 设置此标志将客户端登录，而不通知 MAPI 后台处理程序。 使用此标志登录 MAPI 的客户端无法收到已读状态报告。
  
应MAPI_NO_MAIL设置以下标记：
  
- 如果客户端在会话期间不会发送或接收消息。
    
- 如果客户端可以完全控制配置文件的内容，并且使用紧密耦合的邮件存储和传输提供程序（如 Microsoft 邮件存储提供程序）来Exchange接收邮件。
    
消息客户端可以与非邮件客户端共享会话。 共享会话的一个成员的特征不受其他成员的特征的影响。 也就是说，如果登录时设置了 MAPI_NO_MAIL 和 MAPI_ALLOW_OTHERS 标志，则登录到会话的消息客户端不会影响客户端的操作，反之亦然。 邮件客户端仍将能够发送和接收邮件，客户端将无法发送和接收邮件。
  
**MAPILogonEx** 定义一些可以设置的其他标志： 
  
- MAPI_FORCE_DOWNLOAD **MAPILogonEx** 返回之前应下载传入的邮件。 不设置此标志会导致稍后在后台下载邮件。 
    
- MAPI_SERVICE_UI_ALWAYS请求配置文件中的每个邮件服务显示配置对话框。
    
- MAPI_NT_SERVICE表示您的客户端已作为 Windows 服务实现。 如果客户端是服务，则必须设置此标志。
    
每次成功登录后 **，MAPILogonEx** 都会返回一个指向 MAPI 会话的指针。 可以使用此指针调用 **IMAPISession 接口** 的方法。 有关详细信息，请参阅 [IMAPISession ： IUnknown](imapisessioniunknown.md)。 会话指针（无论会话类型如何）对于接收它们且跨任务无效是唯一的。
  

