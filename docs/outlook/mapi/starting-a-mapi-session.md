---
title: 启动 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7935ebed-f252-482c-ad8c-757aa2d8501d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d88ce382b6a6b5f98ec5f88c4deb1565d3b60151
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336342"
---
# <a name="starting-a-mapi-session"></a>启动 MAPI 会话

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
虽然在会话启动期间执行了大量的工作, 但所需的任务很少。 大部分工作是在[MAPIInitialize](mapiinitialize.md)和[MAPILogonEx](mapilogonex.md)呼叫的 MAPI 处理过程中完成的。 这两个函数都接受标志作为用于控制会话的各个方面 (如通知处理和用户界面) 的输入参数。 在调用**MAPIInitialize**以初始化 mapi 库和**MAPILogonEx**以登录 mapi 子系统时, 请务必了解设置每个标志的后果。 
  
 **启动 MAPI 会话**
  
1. 调用**MAPIInitialize**以初始化 MAPI 库的标准集。 
    
2. 如果需要使用 ole 库, 请调用 ole 函数[OleInitialize](https://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx)。
    
3. 如果需要使用 MAPI 实用工具库, 请调用[ScInitMapiUtil](scinitmapiutil.md)。
    
4. 使用有效的配置文件调用**MAPILogonEx**以登录到 MAPI 子系统。 **MAPILogonEx**验证配置文件中包括的邮件服务中的每个服务提供程序的配置, 并在必要时提示用户提供其他信息。 **MAPILogonEx**完成后, 已配置的服务提供商已准备好进行服务。 
    
## <a name="in-this-section"></a>本节内容

[初始化 MAPI](initializing-mapi.md)
  
> 介绍如何为会话初始化 MAPI。
    
[为 MAPI 初始化 OLE](initializing-ole-for-mapi.md)
  
> 描述为使用 MAPI 初始化 OLE 所要执行的调用。
    
[初始化 MAPI 实用工具](initializing-the-mapi-utilities.md)
  
> 介绍如何初始化 MAPI 实用工具。
    
[登录 MAPI](logging-on-to-mapi.md)
  
> 介绍客户端应用程序如何登录到 MAPI 子系统。
    

