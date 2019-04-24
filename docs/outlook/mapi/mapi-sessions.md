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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319579"
---
# <a name="mapi-sessions"></a>MAPI 会话

**适用于**：Outlook 2013 | Outlook 2016 
  
在客户端应用程序可以调用基础邮件系统之前, 它必须使用 MAPI 子系统建立会话或连接。
  
会话在用户登录时启动, 该过程可访问有效的配置文件, 并验证邮件系统和邮件服务凭据。 然后, 此过程可确保正确配置所有配置文件的邮件服务。 您使用的客户端接口决定了登录呼叫。 MAPI 客户端调用[MAPILogonEx](mapilogonex.md)函数。 
  
邮件服务配置是登录过程中最重要的部分之一。 配置文件是配置信息的初始源。 如果缺少特定邮件服务的信息, 登录过程将尝试提示用户提供此信息。 这并不总是成功, 原因有两个: 首先, 提示用户需要显示对话框。 客户端可以通过将标志传递到登录呼叫来禁止显示用户界面。 其次, 用户可以先取消对话框, 然后再添加所需的信息。
  
当登录过程失败一次时, 用户会收到故障通知, 并将有机会重试或更正错误条件。 同样, 如果客户端允许, 将显示用户界面, 并且系统会提示用户输入丢失的任何数据。 如果第二次尝试失败, MAPI 将在会话期间禁用邮件服务中的所有服务提供程序。 实际上, 整个邮件服务已被禁用。 这意味着邮件服务中的任何服务提供程序都不能正常工作。 这样做是因为如果一个提供程序失败登录, 则其他提供程序通常也会失败。 登录过程可能会失败, 因为所需资源的路径无效、MAPI 的不兼容版本、不可用的邮件服务器或数据损坏。 
  
客户端可以指定在登录呼叫中建立的两种会话类型之一: 单个会话或共享会话。 单个会话是专用连接;客户端应用程序和它使用的会话之间存在一对一的关系。 因此, 共享会话的客户端应用程序也共享配置文件。 共享会话已建立一次, 但可供需要使用它们的其他客户端应用程序使用。 配置文件和凭据仅在初始登录时指定。 
  
客户端可以作为同一个用户或多个用户登录多次。 MAPI 不会阻止这种情况发生。 但是, 某些服务提供程序可能不会很灵活, 在后续登录尝试中返回错误值 MAPI_E_SESSION_LIMIT。 可能需要具有基础硬件限制的服务提供程序才能强制实施会话限制。
  
用于建立会话的函数调用具有一个标志和参数的集合, 用于控制会话的创建方式。 客户端指定一个可选的配置文件名称和一个窗口句柄, 用作显示的任何对话框的父窗口。 这些标志包括 MAPI_NEW_SESSION, 后者请求建立新的单个会话 (而不是共享会话) 和 MAPI_LOGON_UI 用户界面标志。 将用户界面标志设置为 "请求登录" 对话框。
  
下图显示了这些不同的参数和标志如何建立 MAPI 会话。
  
**MAPI 会话流程图**
  
![MAPI 会话流程图](media/amapi_47.gif "MAPI 会话流程图")
  
有关在客户端应用程序中处理会话的信息, 请参阅[MAPI 会话处理](mapi-session-handling.md)
  
## <a name="see-also"></a>另请参阅

- [MAPILogonEx](mapilogonex.md)  
- [IMAPISession : IUnknown](imapisessioniunknown.md)
- [MAPI 会话处理](mapi-session-handling.md)  
- [MAPI 编程概述](mapi-programming-overview.md)

