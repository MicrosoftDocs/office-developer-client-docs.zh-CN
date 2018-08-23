---
title: 开发 MAPI 客户端应用程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bcb59b08-e6d7-4739-8cb5-e545bd0d478f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bffcfdd6d688c483655b97d61075b147430e3fcc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564974"
---
# <a name="developing-a-mapi-client-application"></a>开发 MAPI 客户端应用程序

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 客户端应用程序是编写的面向对象的 MAPI 客户端接口。 MAPI 客户端与通过 MAPI 子系统和 MAPI 兼容的服务提供商的一个或多个邮件系统进行交互。 多种不同的方式; 中可能发生这种交互客户端应用程序中没有巨大的各种。 大多数客户端的消息客户端，可以将集成到其已建立的功能集中消息或执行消息作为其主要功能。 MAPI 客户端可能提供其他功能包括配置文件管理或通讯簿和消息存储管理。
  
所有消息客户端初始化 MAPI 库，并开始与 MAPI 子系统**会话**。 有关详细信息，请参阅[使用会话访问对象](accessing-objects-by-using-the-session.md)。 在建立会话后，客户端可以：
  
- 处理传出邮件，包括答复，转发邮件和重新传输。
    
- 处理传入消息。
    
- 处理通过打开文件夹和邮件、 创建、 修改、 复制和发送邮件、 跟踪对话和搜索一个或多个文件夹的邮件存储区。
    
- 创建和修改收件人、 查找条目，并将遍历容器层次结构通过以下方式处理通讯簿。
    
- 通过执行重新配置、 设置选项和传输顺序，并根据需要发送邮件处理传输提供程序。
    
- 处理事件通知。
    
- 处理窗体。
    
- 处理配置文件和消息服务。
    
使用本节中的主题可帮助您实现这些基本任务和特定功能使您的 MAPI 客户端唯一。
  

