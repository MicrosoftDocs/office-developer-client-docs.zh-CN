---
title: 支持邮件服务安装
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 822e07bc-0bca-4485-8938-2264315161e2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bf3e79ad32801a659df2c68016167d3b547ddc6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778914"
---
# <a name="supporting-message-service-installation"></a>支持邮件服务安装

  
  
**适用于**： Outlook 
  
安装您的消息服务的安装程序应执行以下操作：
  
1. 将邮件服务文件，如消息服务和服务提供商 Dll，从 CD 或磁盘，复制到本地驱动器工作站上。 需要将复制的文件取决于您的消息服务。 通常将复制至少一个 DLL。
    
2. 将项添加到 Mapisvc.inf 配置文件。 有关如何修改此文件以在邮件服务中支持的服务提供程序的详细信息，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。
    
3. 根据需要对系统注册表对邮件服务添加条目。 有关条目应在系统注册表中的显示方式的详细信息，请参阅[安装 MAPI 子系统](installing-the-mapi-subsystem.md)。
    
4. 创建默认配置文件，如果一个尚不存在使用以下各项之一：
    
  - 要使用的对话框一系列用户交互创建一个配置文件的配置文件向导。 有关使用配置文件向导的详细信息，请参阅[创建一个配置文件使用配置文件向导](creating-a-profile-by-using-the-profile-wizard.md)。
    
  - 创建配置文件使用用户交互 Control Panel。 控制面板中，向用户提供用于配置消息服务和设置配置文件属性配置文件向导比更大的灵活性。 
    
将指定的公共目录中安装程序。 这是目录的重要，因为大多数配置客户端，如控制面板中，要求用户输入的名称。 当用户单击**添加**按钮，调用**从磁盘**对话框中，并指定该程序的路径，则控制面板调用安装程序。 控制面板运行程序，并调用_ulContext_参数设置为 MSG_SERVICE_INSTALL 消息服务的入口点函数。 
  
> [!CAUTION]
> 由于配置文件的 MAPI 体系结构可丢弃组成部分，确保您的安装程序不存储任何很难重新创建默认配置文件中。 有配置文件恢复的、 用于将配置文件从一台计算机移到另一个、 脱机备份或个人或全局备份副本还原为未实用程序。 
  
## <a name="see-also"></a>另请参阅



[邮件服务实现](message-service-implementation.md)

