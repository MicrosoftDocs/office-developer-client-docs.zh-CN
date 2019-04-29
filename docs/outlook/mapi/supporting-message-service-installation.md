---
title: 支持邮件服务安装
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 822e07bc-0bca-4485-8938-2264315161e2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 328884e8758e679eb1c9d968547cba02c01d4d47
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404699"
---
# <a name="supporting-message-service-installation"></a>支持邮件服务安装

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
安装邮件服务的安装程序应执行以下操作:
  
1. 将邮件服务文件 (如邮件服务和服务提供程序 dll) 从 CD 或磁盘复制到工作站上的本地驱动器。 需要复制的文件取决于您的邮件服务。 通常情况下, 至少要复制一个 DLL。
    
2. 将条目添加到 mapisvc.inf 配置文件。 有关如何修改此文件以支持邮件服务中的服务提供程序的详细信息, 请参阅[mapisvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。
    
3. 根据需要将条目添加到邮件服务的系统注册表中。 有关这些条目应如何显示在系统注册表中的详细信息, 请参阅[安装 MAPI 子系统](installing-the-mapi-subsystem.md)。
    
4. 如果一个默认配置文件尚不存在, 请使用以下项目之一创建该配置文件:
    
  - 配置文件向导通过使用用户在一系列对话框中进行交互来创建配置文件。 有关使用配置文件向导的详细信息, 请参阅[使用配置文件向导创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。
    
  - 使用 "用户交互" 创建配置文件的 "控制面板"。 "控制面板" 提供的用户比配置邮件服务和设置配置文件属性的配置文件向导具有更大的灵活性。 
    
将安装程序放在指定的公用目录中。 这一点很重要, 因为大多数配置客户端 (如控制面板) 要求用户输入目录的名称。 当用户单击 "**添加**" 按钮时, 控制面板将调用安装程序, 同时调用 "**有磁盘**" 对话框, 并指定程序的路径。 "控制面板" 运行程序, 并调用您的邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_INSTALL。 
  
> [!CAUTION]
> 由于配置文件是 MAPI 体系结构的一个 expendable 部分, 因此, 请确保您的安装程序不会在默认配置文件中存储难以重新创建的任何内容。 没有用于配置文件恢复的实用程序, 用于将配置文件从一台计算机移动到另一台计算机, 用于脱机备份, 或从备份副本进行个人或全局还原。 
  
## <a name="see-also"></a>另请参阅



[邮件服务实现](message-service-implementation.md)

