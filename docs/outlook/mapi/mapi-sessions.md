---
title: MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c5a7c137-393e-40ff-a2b9-afe02da2435a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3dd55d8ee3cb2751fb27184f0069ae831e2164ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435871"
---
# <a name="mapi-sessions"></a>MAPI 会话

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序必须先与 MAPI 子系统建立会话或连接，然后客户端应用程序才能调用基础邮件系统。
  
会话在用户登录时启动，这是一个访问有效配置文件并验证邮件系统和邮件服务凭据的过程。 然后，此过程可确保配置文件的所有邮件服务都配置正确。 使用的客户端接口确定登录调用。 MAPI 客户端调用 [MAPILogonEx](mapilogonex.md) 函数。 
  
邮件服务配置是登录过程最重要的部分之一。 配置文件是配置信息的初始源。 如果缺少特定邮件服务的信息，登录过程将尝试提示用户提供该信息。 这并非总是成功的原因有两个：第一，提示用户需要显示对话框。 客户端可以通过将标志传递到登录调用来禁止显示用户界面。 其次，用户可以在添加所需信息之前取消对话框。
  
当登录过程失败一次时，将通知用户失败，并给予用户重试或更正错误条件的机会。 同样，如果客户端允许，将显示用户界面，并提示用户输入缺少的任何数据。 如果第二次尝试失败，MAPI 在会话期间将禁用邮件服务中所有服务提供程序。 实际上，整个邮件服务处于禁用状态。 这意味着邮件服务中的服务提供程序均无法工作。 这样做的原因是，如果一个提供程序登录失败，其他提供程序通常也会失败。 登录过程可能由于必要资源的路径无效、MAPI 版本不兼容、消息服务器不可用或数据损坏而失败。 
  
客户端可以指定在登录调用中要建立的两种类型的会话之一：单个会话或共享会话。 单个会话是专用连接;客户端应用程序与它使用的会话之间存在一对一关系。 因此，共享会话的客户端应用程序也会共享配置文件。 共享会话建立一次，但需要使用它们的其他客户端应用程序可以使用。 配置文件和凭据仅在初始登录时指定。 
  
客户端可以同一用户或多个用户登录多次。 MAPI 不会阻止此操作。 但是，某些服务提供商可能不够灵活，在后续登录尝试MAPI_E_SESSION_LIMIT错误值。 可能需要具有基础硬件限制的服务提供商才能强制执行会话限制。
  
建立会话的函数调用具有控制会话创建方式的标志和参数集合。 客户端指定一个可选的配置文件名称和一个充当所显示任何对话框的父窗口的窗口句柄。 标志包括MAPI_NEW_SESSION，请求建立新的单个会话 (而不是共享会话) ，以及 MAPI_LOGON_UI 用户界面标志。 用户界面标志设置为请求登录对话框。
  
下图显示了这些不同的参数和标志如何建立 MAPI 会话。
  
**MAPI 会话流程图**
  
![MAPI 会话流程图](media/amapi_47.gif "MAPI 会话流程图")
  
有关从客户端应用程序内处理会话的信息，请参阅 [MAPI 会话处理](mapi-session-handling.md)
  
## <a name="see-also"></a>另请参阅

- [MAPILogonEx](mapilogonex.md)  
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MAPI 会话处理](mapi-session-handling.md)  
- [MAPI 编程概述](mapi-programming-overview.md)

