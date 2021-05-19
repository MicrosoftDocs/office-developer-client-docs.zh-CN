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
  
尽管会话启动期间执行大量工作，但所需任务最少。 大部分工作是在 [MAPIInitialize](mapiinitialize.md) 和 [MAPILogonEx 调用的 MAPI](mapilogonex.md) 处理中完成。 这两个函数均接受标志作为输入参数，用于控制会话的各个方面，如通知处理和用户界面。 在调用 **MAPIInitialize** 以初始化 MAPI 库和 **MAPILogonEx** 以登录到 MAPI 子系统时，了解设置每个标志的后果非常重要。 
  
 **启动 MAPI 会话**
  
1. 调用 **MAPIInitialize** 以初始化标准 MAPI 库集。 
    
2. 如果需要使用 OLE 库，请调用 OLE 函数 [OleInitialize](https://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx)。
    
3. 如果需要使用 MAPI 实用工具库，请调用 [ScInitMapiUtil](scinitmapiutil.md)。
    
4. 使用有效的配置文件调用 **MAPILogonEx** 以登录到 MAPI 子系统。 **MAPILogonEx** 验证配置文件中包含的邮件服务中每个服务提供程序的配置，并在必要时并可能提示用户输入其他信息。 **MAPILogonEx** 完成后，配置的服务提供程序即可供服务使用。 
    
## <a name="in-this-section"></a>本节内容

[初始化 MAPI](initializing-mapi.md)
  
> 介绍如何初始化会话的 MAPI。
    
[为 MAPI 初始化 OLE](initializing-ole-for-mapi.md)
  
> 描述初始化 OLE 以与 MAPI 一同使用的调用。
    
[初始化 MAPI 实用工具](initializing-the-mapi-utilities.md)
  
> 介绍如何初始化 MAPI 实用工具。
    
[登录 MAPI](logging-on-to-mapi.md)
  
> 描述客户端应用程序如何登录到 MAPI 子系统。
    

