---
title: 启动 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7935ebed-f252-482c-ad8c-757aa2d8501d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9e95423a1aa9a04247a70592a797d2395cafecc4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595368"
---
# <a name="starting-a-mapi-session"></a>启动 MAPI 会话

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
虽然大量会话开始备份过程中执行，但需要执行的任务是操作的最少。 MAPI 中完成的此工作的大部分[MAPIInitialize](mapiinitialize.md)和[MAPILogonEx](mapilogonex.md)呼叫处理。 这两个这些函数接受作为输入参数的控制的会话的用户界面通知处理等方面的标志。 若要了解调用**MAPIInitialize**初始化 MAPI 库和**MAPILogonEx**用于登录到 MAPI 子系统时设置每个这些标志的后果至关重要。 
  
 **若要启动的 MAPI 会话**
  
1. 调用**MAPIInitialize**初始化一组标准的 MAPI 库。 
    
2. 如果您需要使用 OLE 库，请调用 OLE 函数[OleInitialize](http://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx)。
    
3. 如果您需要使用 MAPI 实用程序库，请调用[ScInitMapiUtil](scinitmapiutil.md)。
    
4. 一个有效的配置文件，用于登录到 MAPI 子系统调用**MAPILogonEx** 。 **MAPILogonEx**验证每个提示用户提供其他信息，如果必要，并且可能在配置文件中包含的邮件服务中的服务提供程序的配置。 **MAPILogonEx**完成后，配置的服务提供商可供服务。 
    
## <a name="in-this-section"></a>本节内容

[初始化 MAPI](initializing-mapi.md)
  
> 介绍如何为会话初始化 MAPI。
    
[初始化 MAPI 的 OLE](initializing-ole-for-mapi.md)
  
> 介绍呼叫发出 MAPI 用于初始化 OLE。
    
[初始化 MAPI 实用工具](initializing-the-mapi-utilities.md)
  
> 介绍如何初始化 MAPI 实用程序。
    
[登录到 MAPI](logging-on-to-mapi.md)
  
> 介绍如何客户端应用程序登录到 MAPI sub 系统。
    

