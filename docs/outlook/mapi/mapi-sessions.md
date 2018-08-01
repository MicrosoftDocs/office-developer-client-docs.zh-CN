---
title: MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c5a7c137-393e-40ff-a2b9-afe02da2435a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 45dc993c337249ed7d4dffbd5324267de82981d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776328"
---
# <a name="mapi-sessions"></a>MAPI 会话

**适用于**： Outlook 
  
客户端应用程序可以调用基础的消息系统之前，它必须建立一个会话或连接，与 MAPI 子系统。
  
用户登录后访问有效的配置文件，并验证邮件系统和消息服务凭据的过程启动会话。 然后，此过程可确保所有配置文件的消息服务都正确配置。 您使用的客户端接口确定登录呼叫。 MAPI 客户端调用[MAPILogonEx](mapilogonex.md)函数。 
  
登录过程的最重要的部分之一消息服务配置。 配置文件是配置信息的初始源。 如果缺少特定消息服务的信息，则登录过程会尝试提示用户提供该文件。 这并不总是成功原因有二： 首先，提示用户需要的对话框中显示。 使客户端可以通过将一个标志传递到登录呼叫禁用用户界面的显示它。 其次，用户无法取消对话框之前可以添加所需的信息。
  
如果登录过程失败一次，用户为失败的通知，并机会重试或更正错误条件。 同样，用户界面将显示，如果客户端允许，并且将提示用户输入的任何数据丢失了。 如果此第二个尝试失败，MAPI 禁用消息服务的会话的持续时间中的所有服务提供商。 实际上，整个邮件服务被禁用。 这意味着无邮件服务的服务提供商可以进行处理。 这是因为如果一个提供程序失败登录，其他提供程序通常也会失败。 由于无效的路径所需的资源，MAPI，不可用的消息服务器或数据损坏的不兼容版本，登录过程可能会失败。 
  
客户端可以指定登录呼叫中建立的会话的两种类型之一： 单个会话或共享的会话。 单个会话的专用连接;没有一对一关系的客户端应用程序和它使用的会话。 因此，客户端应用程序共享会话还共享一个配置文件。 共享的会话建立一次，但可以由其他客户端应用程序需要使用它们。 仅使用初始登录指定的配置文件和凭据。 
  
客户端可以登录多次作为同一个用户或多个用户。 MAPI 不阻止此。 某些服务提供商，但是，可能不是为灵活，返回错误值 MAPI_E_SESSION_LIMIT 在以后的登录尝试次数。 与基础硬件限制的服务提供商需要强制实施会话限制。
  
建立一个会话的函数调用具有标志和参数的集合，如何创建会话的控制权。 客户端指定可选的配置文件的名称和用作父窗口的任何对话框的显示窗口句柄。 Flags 包括 MAPI_NEW_SESSION，请求，建立新的单个会话 （而不是共享的会话），以及 MAPI_LOGON_UI 用户界面标志。 用户界面标志设置为请求的登录对话框。
  
下图显示了如何这些各种参数和标志建立的 MAPI 会话。
  
**MAPI 会话流程图**
  
![MAPI 会话流程图](media/amapi_47.gif "MAPI 会话流程图")
  
有关处理来自客户端应用程序内的会话的信息，请参阅[MAPI 会话处理](mapi-session-handling.md)
  
## <a name="see-also"></a>另请参阅

- [MAPILogonEx](mapilogonex.md)  
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MAPI 会话处理](mapi-session-handling.md)  
- [MAPI 编程概述](mapi-programming-overview.md)

