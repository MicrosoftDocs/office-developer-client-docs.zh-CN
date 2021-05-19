---
title: 关于包装的 PST 存储提供程序示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: 779dd96c4f07c0c5eee60ae046cd17db98eebfd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432721"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a>关于包装的 PST 存储提供程序示例

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
## <a name="overview-of-message-store-providers"></a>邮件存储提供程序概述

邮件存储提供程序为客户端应用程序的用户处理邮件和其他信息的存储和检索。 邮件信息使用称为邮件存储的分层系统进行组织。 邮件存储在多个级别实现，其中容器称为文件夹，用于保存不同类型的邮件。 对邮件存储中的级别数没有限制;文件夹可以包含许多子文件夹。
  
邮件存储数据可通过多种方式使用。 除了典型的电子邮件用法之外，文件夹还可以用作公共讨论论坛、参考文档存储库或公告板信息的容器。 一个邮件存储可以保存许多类型的信息，一些是可修改的，有些则不能。 多个客户端可以安装同一个邮件存储，从而方便且快速共享数据。
  
邮件存储文件夹允许你对邮件进行排序和筛选，并自定义用户界面中的视图 (UI) 显示。 筛选邮件的链接位于名为"搜索结果文件夹"的特殊文件夹中。 客户端应用程序的用户输入筛选条件，MAPI 作为限制引用，并且条件应用于存储在一个或多个文件夹中的邮件。 例如，用户可能只希望查看那些处理特定主题的邮件（到达日期比上周最近）。 对匹配条件的邮件的引用列在搜索结果文件夹中，真实邮件仍保留在常规文件夹中。
  
消息是从一个用户或应用程序传输到另一个用户或应用程序的数据的单位。 每封邮件都包含一些用于传输的邮件文本和邮件信封信息。 某些邮件包括一个或多个附件，或者与文件、其他邮件或 OLE 对象形式的邮件相关且与邮件一起传输的其他数据。
  
## <a name="the-sample-wrapped-pst-store-provider"></a>包装的 PST 存储提供程序示例

复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储。 使用复制 API 将数据复制到专用 PST 存储并跟踪同步状态。 此方法不要求引入自定义 MAPI 存储提供程序，该提供程序编写和维护比较复杂。 但是，PST 存储提供程序确实需要包装，以使用复制 API。
  
包装的 PST 存储提供程序示例使用 PST (PST) 文件作为存储数据的后端。 包装的 PST 存储提供程序应该与复制 API 结合使用。 有关详细信息，请参阅[关于复制 API。](about-the-replication-api.md) 示例包装 PST 存储提供程序中的大多数函数都直接将参数传递给基础 PST 提供程序。 某些函数需要特殊实现，以下主题对此进行了介绍。
  
## <a name="in-this-section"></a>本节内容

- [安装包装的 PST 存储提供程序示例](installing-the-sample-wrapped-pst-store-provider.md)
    
- 介绍如何下载和安装包装示例 PST 存储提供程序。
    
- [初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- 实现包装的 PST 存储提供程序的第一步是初始化和配置封装的 PST 存储提供程序。
    
- [登录到包装的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- 初始化包装的 PST 存储提供程序后，必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到包装的 PST 存储提供程序。
    
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
    
- 若要使用包装的 PST 存储提供程序，必须包装 **[IMAPISupport：：IUnknown](imapisupportiunknown.md)** 接口来实现常见的封装 PST 存储提供程序任务。 
    
- [关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
- 使用包装的 PST 存储提供程序完成后，必须正确关闭包装的 PST 存储提供程序。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

