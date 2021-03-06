---
title: 开发 MAPI 客户端应用程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bcb59b08-e6d7-4739-8cb5-e545bd0d478f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f66d2e4d46519dd186a676a0d0fbb836322893b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410033"
---
# <a name="developing-a-mapi-client-application"></a>开发 MAPI 客户端应用程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 客户端应用程序是使用面向对象的 MAPI 客户端接口编写的。 MAPI 客户端通过 MAPI 子系统和符合 MAPI 的服务提供商与一个或多个邮件系统交互。 这种交互可能以许多不同的方式发生;客户端应用程序中有很多种。 大多数客户端都是消息客户端，将消息传递集成到其已建立的功能集或将消息传递作为其主要功能。 MAPI 客户端可能提供的其他功能包括配置文件管理、通讯簿和邮件存储管理。
  
所有邮件客户端初始化 MAPI 库，并启动与MAPI 子系统的会话。 有关详细信息，请参阅 [使用会话访问对象](accessing-objects-by-using-the-session.md)。 建立会话后，客户端可以：
  
- 处理传出邮件，包括答复、转发的邮件和重新传输。
    
- 处理传入邮件。
    
- 通过打开文件夹和邮件、创建、修改、复制和发送邮件、跟踪对话以及搜索一个或多个文件夹来处理邮件存储。
    
- 通过创建和修改收件人、定位条目和遍历容器层次结构来处理通讯簿。
    
- 通过执行重新配置、设置选项和传输顺序以及按需发送邮件来处理传输提供程序。
    
- 处理事件通知。
    
- 处理表单。
    
- 处理配置文件和邮件服务。
    
使用本节中的主题可帮助你实现这些基本任务和使 MAPI 客户端独一无二的特定功能。
  

