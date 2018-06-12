---
title: 登录到 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 05bafe43-a78a-4659-92f0-0b4fe444c64f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ae3c47964ff238f57e98e0005a966008192f7c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776165"
---
# <a name="logging-on-to-mapi"></a>登录到 MAPI
 
**适用于**： Outlook 
  
客户端应用程序登录到 MAPI 子系统调用**MAPILogonEx**函数。 有关详细信息，请参阅[MAPILogonEx](mapilogonex.md)。 **MAPILogonEx**验证所选的模板和配置文件中每个服务提供程序的配置。 配置后，MAPI 开始消息存储提供程序之前通讯簿提供程序。 首先需要其服务时才会启动传输提供程序。 
  
## <a name="choose-a-profile"></a>选择一个配置文件
  
- 代表**MAPILogonEx**， _lpszProfileName_参数中的配置文件的名称的字符串中传递或...
    
- 允许用户通过_lpszProfileName_参数中传递 NULL 并设置 MAPI_LOGON_UI 标志，指定的配置文件或... 

- 选择默认配置文件通过_lpszProfileName_参数中传递 NULL 并设置 MAPI_USE_DEFAULT 标志。 
    
如果您需要特定配置文件的默认配置文件之外，必须在您自己的配置数据库中保存其名称或使用特定的命名约定。 MAPI 不公开在配置文件表中，名称和默认标记以外的任何配置文件属性和默认配置文件标志供消息客户端和相关的 IPM 应用程序。
  
提供部分的配置文件或**MAPILogonEx**提供程序配置信息的客户端必须从而将显示一个对话框提示用户输入其他数据。 如果缺少信息且**MAPILogonEx**无法提示用户提供其登录失败。 执行不需要用户输入的客户端可以禁止对话框框显示。 
  
**MAPILogonEx**使用启用的用户界面的标志相互排斥;可以设置只有一个。 保留这些标志未设置禁止显示用户界面，导致**MAPILogonEx**失败如果缺少必需的信息。 也就是说，如果您禁用用户界面和为_lpszProfileName_参数传递 NULL 并不设置 MAPI_USE_DEFAULT 标志， **MAPILogonEx**将失败，因为它无法检索配置文件名称。 
  
**MAPILogonEx**建立会话可以是单个消息会话、 共享的邮件会话或非邮件会话。 单个消息的会话专用您的客户端和 MAPI 子系统之间的连接，可以通过对**MAPILogonEx**的调用中设置 MAPI_NEW_SESSION 标志来建立。
  
共享的邮件会话是多个邮件客户端可以使用的连接。 共享的会话通常建立的客户端使用的同一配置文件。 若要将新的会话为共享会话，请设置 MAPI_ALLOW_OTHERS 标志。 
  
## <a name="use-an-existing-shared-session"></a>使用现有共享的会话
  
- 未设置 MAPI_NEW_SESSION 标志。
    
- 未设置 MAPI_ALLOW_OTHERS 标志。
    
- 为_lpszProfileName_参数传递 NULL。 
    
- 为_lpszPassword_参数传递 NULL。 
    
非邮件会话允许客户端访问 MAPI 子系统，但不是允许发送或接收邮件。 配置或管理应用程序可能需要建立非邮件会话的客户端的示例。 要请求的非邮件会话，请设置 MAPI_NO_MAIL 标志。 设置此标志以在登录您的客户端，但没有告知 MAPI 后台处理程序。 使用此标志登录到 MAPI 的客户端无法希望以往接收读取的状态报告。
  
只应设置 MAPI_NO_MAIL 标志：
  
- 如果您的客户端将不发送或在会话过程中接收邮件。
    
- 如果您的客户端具有完全控制配置文件的内容和发送和接收消息使用紧密耦合消息存储，并且传输提供程序，如 Microsoft Exchange 提供商。
    
消息客户端可以与非邮件客户端共享会话。 共享会话的一个成员的特征不受影响的其他成员的特征。 也就是说，如果 MAPI_NO_MAIL 和 MAPI_ALLOW_OTHERS 设置 flags 登录，登录到您的会话的消息客户端对没有影响操作的客户端，反之亦然。 消息客户端将仍无法发送和接收邮件，并无法与您的客户端。
  
**MAPILogonEx**定义几个您可以设置其他标志： 
  
- MAPI_FORCE_DOWNLOAD 指示**MAPILogonEx**返回之前，应下载传入消息。 不设置此标志会导致在以后在后台下载的邮件。 
    
- MAPI_SERVICE_UI_ALWAYS 请求配置文件中的每个邮件服务显示的配置对话框。
    
- MAPI_NT_SERVICE 指示您的客户端实现作为 Windows 服务。 如果您的客户端是一项服务，必须设置此标志。
    
与每个成功登录**MAPILogonEx**返回到 MAPI 会话的指针。 您可以使用此指针调用**IMAPISession**接口的方法。 有关详细信息，请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。 会话指针，无论，类型是会话的唯一的客户端接收这些且不是会话的有效跨任务。
  

