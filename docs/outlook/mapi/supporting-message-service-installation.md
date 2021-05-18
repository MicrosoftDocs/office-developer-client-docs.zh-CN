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
  
用于安装邮件服务的安装程序应执行以下操作：
  
1. 将邮件服务文件（如邮件服务和服务提供程序 DLL）从 CD 或磁盘复制到工作站上的本地驱动器。 需要复制的文件取决于您的邮件服务。 通常，你将复制至少一个 DLL。
    
2. 将条目添加到 Mapisvc.inf 配置文件。 若要详细了解如何修改此文件以支持邮件服务中的服务提供程序，请参阅 File Format of [MapiSvc.inf](file-format-of-mapisvc-inf.md)。
    
3. 根据需要将条目添加到邮件服务的系统注册表中。 有关条目在系统注册表中的显示方式详细信息，请参阅 [安装 MAPI 子系统](installing-the-mapi-subsystem.md)。
    
4. 如果尚不存在默认配置文件，则使用下列项目之一创建一个：
    
  - 通过一系列对话框使用用户交互创建配置文件的配置文件向导。 有关使用配置文件向导的信息，请参阅使用配置文件向导 [创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。
    
  - 使用用户交互创建配置文件的控制面板。 与配置文件向导一样，控制面板为用户配置邮件服务和设置配置文件属性提供了更大的灵活性。 
    
将安装程序放在指定的公用目录中。 这一点很重要，因为大多数配置客户端（如控制面板）都要求用户输入目录的名称。 当用户单击"添加"按钮时，控制面板将调用安装程序，调用"拥有磁盘"对话框，并指定程序的路径。 控制面板运行程序并调用邮件服务的入口点函数  _，ulContext_ 参数设置为 MSG_SERVICE_INSTALL。 
  
> [!CAUTION]
> 由于配置文件是 MAPI 体系结构的一部分，因此请确保你的安装程序不会在默认配置文件中存储任何难以重新创建的信息。 没有用于配置文件恢复、将配置文件从一台计算机移动到另一台计算机、进行外线备份或者从备份副本中执行单个或全局还原的实用工具。 
  
## <a name="see-also"></a>另请参阅



[邮件服务实现](message-service-implementation.md)

