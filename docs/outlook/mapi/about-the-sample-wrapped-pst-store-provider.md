---
title: 关于示例包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: 779dd96c4f07c0c5eee60ae046cd17db98eebfd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432721"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a>关于示例包装的 PST 存储区提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
## <a name="overview-of-message-store-providers"></a>邮件存储区提供程序概述

邮件存储提供程序处理邮件的存储和检索以及客户端应用程序用户的其他信息。 邮件信息通过使用称为 "邮件存储库" 的分层系统进行组织。 邮件存储在多个级别中实现, 容器称为文件夹, 其中包含不同类型的邮件。 对邮件存储区中的级别数没有限制;文件夹可以包含多个子文件夹。
  
可以通过多种方式使用邮件存储区数据。 除了典型的电子邮件使用之外, 还可以将文件夹用作公开讨论的论坛, 作为参考文档的存储库, 或作为公告板信息的容器。 单个邮件存储区可以包含多种类型的信息, 一些是可修改的, 有些则不是。 多个客户端可以安装相同的邮件存储, 从而轻松快速地共享数据。
  
邮件存储文件夹允许您对邮件进行排序和筛选, 并在用户界面 (UI) 显示中自定义视图。 筛选出的邮件的链接保存在称为搜索结果文件夹的特殊文件夹中。 客户端应用程序的用户输入筛选条件, MAPI 将其称为限制, 并将条件应用于存储在一个或多个文件夹中的邮件。 例如, 用户可能只想查看那些处理到达日期晚于上周的特定主题的邮件。 对与条件匹配的邮件的引用在搜索结果文件夹中列出, 实际邮件仍保留在其常规文件夹中。
  
消息是从一个用户或应用程序传输到另一个用户或应用程序的数据的单位。 每封邮件都包含一些用于传输的邮件文本和邮件信封信息。 某些邮件包含一个或多个附件, 或与文件、另一封邮件或 OLE 对象的形式的邮件一起传输的或与之传输的其他数据。
  
## <a name="the-sample-wrapped-pst-store-provider"></a>包装的 PST 存储区提供程序示例

复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储。 您可以使用复制 API 将数据复制到专用的 PST 存储, 并跟踪同步状态。 此方法不要求您引入自定义 MAPI 存储提供程序, 这对编写和维护非常复杂。 但是, PST 存储提供程序需要进行包装以使用复制 API。
  
示例包装的 PST 存储区提供程序使用个人文件夹文件 (PST) 提供程序作为存储数据的后端。 包装的 PST 存储区提供程序应与复制 API 结合使用。 有关详细信息, 请参阅[关于复制 API](about-the-replication-api.md)。 示例包装的 pst 存储提供程序中的大多数函数将其参数直接传递给基础 PST 提供程序。 某些函数需要特殊实现, 以下主题对此进行了说明。
  
## <a name="in-this-section"></a>本节内容

- [安装示例包装的 PST 存储区提供程序](installing-the-sample-wrapped-pst-store-provider.md)
    
- 介绍如何下载和安装示例包装的 PST 存储区提供程序。
    
- [初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- 实现打包的 pst 存储提供程序的第一步是初始化和配置打包的 pst 存储区提供程序。
    
- [登录到打包的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- 在包装的 pst 存储区提供程序初始化之后, 您必须实现功能, 以便 mapi 和 mapi 后台处理程序可以登录到打包的 pst 存储提供程序。
    
- [使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)
    
- 若要使用包装的 PST 存储区提供程序, 必须包装**[IMAPISupport:: IUnknown](imapisupportiunknown.md)** 接口以实现常见的打包 PST 存储提供程序任务。 
    
- [关闭打包的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
- 使用包装的 pst 存储区提供程序完成后, 必须正确关闭包装的 pst 存储区提供程序。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

