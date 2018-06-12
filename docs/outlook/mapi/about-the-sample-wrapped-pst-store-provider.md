---
title: 有关示例包装 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 51aef9d8778997749e401b008ebdb4126a248ee0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774474"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a>有关示例包装 PST 存储提供程序

 
  
**适用于**： Outlook 
  
## <a name="overview-of-message-store-providers"></a>消息存储提供程序概述

消息存储提供程序处理对存储和检索的邮件和其他用户的客户端应用程序的信息。 使用称为的消息存储的分层系统，邮件信息的排列方式。 消息存储在多个级别实现与名为保留的不同类型的消息的文件夹的容器。 没有为邮件存储区; 中的级别数限制文件夹可以包含很多子文件夹。
  
消息存储数据可以采用多种方式。 典型的电子邮件使用率，除了作为公共讨论的论坛、 参考文档的库或布告栏信息的容器，则可使用文件夹。 许多类型的信息，一些可修改和不可以保留的单个消息存储。 多个客户端可以安装相同的消息存储库，使其轻松和快速共享数据。
  
消息存储文件夹允许进行排序和筛选消息和自定义中的用户界面 (UI) 显示的视图。 指向筛选的邮件保存在名为搜索结果文件夹的特殊文件夹中。 客户端应用程序的用户输入筛选条件，其中 MAPI 指限制和条件应用于一个或多个文件夹中存储的消息。 例如，用户可能想要查看这些处理与到达日期晚于上一周的特定主题的邮件。 搜索结果文件夹中列出引用符合条件的邮件和实际的邮件保留在其正则文件夹。
  
邮件是从一个用户或另一个用户或应用程序的应用程序传送的数据的单位。 每个邮件包含一些消息文本和用于传输邮件信封信息。 某些消息包括一个或多个附件或其他数据与传输的文件，另一条消息或 OLE 对象形式一条消息。
  
## <a name="the-sample-wrapped-pst-store-provider"></a>本示例自动换行 PST 存储提供程序

复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储区。 您使用复制 API 数据复制到专用的 PST 存储并跟踪的同步状态。 此方法不需要您要引入的自定义的 MAPI 存储提供，即复杂编写和维护。 但是，PST 存储提供程序需要使用复制 API 换行。
  
示例自动换行 PST 存储提供程序存储数据作为后端使用的个人文件夹文件 (PST) 提供程序。 应与复制 API 结合使用的换行的 PST 存储提供程序。 有关详细信息，请参阅[有关复制 API](about-the-replication-api.md)。 大部分示例自动换行 PST 存储提供程序中的函数及其参数直接传递到基础太平洋标准时间提供程序。 某些功能需要特殊的实现，并且以下主题所述。
  
## <a name="in-this-section"></a>本节内容

- [安装示例自动换行 PST 存储提供程序](installing-the-sample-wrapped-pst-store-provider.md)
    
- 介绍如何下载并安装示例自动换行 PST 存储提供程序。
    
- [初始化换行的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- 实现包装的 PST 存储提供程序的第一步是初始化和配置的换行的 PST 存储提供程序。
    
- [登录到换行的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- 初始化换行的 PST 存储提供程序后，您必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到的换行的 PST 存储提供程序。
    
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
    
- 若要使用换行的 PST 存储提供程序必须打包**[IMAPISupport::IUnknown](imapisupportiunknown.md)** 界面，以实现常见换行 PST 存储提供程序任务。 
    
- [关机的情况下被环绕的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
- 使用换行的 PST 存储提供程序之后，您必须正确关闭的换行的 PST 存储提供程序。
    
## <a name="see-also"></a>另请参阅



[有关复制 API](about-the-replication-api.md)
  
[开发 MAPI 消息存储提供程序](developing-a-mapi-message-store-provider.md)

