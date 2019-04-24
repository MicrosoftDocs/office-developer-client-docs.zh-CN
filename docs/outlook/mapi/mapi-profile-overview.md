---
title: MAPI 配置文件概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d6c57be6-2397-4ab1-a912-028454dffc44
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e196800b717ce2528da4b9871bad7425f3a2c326
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328160"
---
# <a name="mapi-profile-overview"></a>MAPI 配置文件概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
配置文件是有关邮件服务和服务提供商的信息的集合, 客户端应用程序的用户希望在特定的 MAPI 会话中提供该信息。 每个用户至少有一个配置文件;许多用户会保留多个。 例如, 用户可能有一个配置文件与基于服务器的邮件存储服务和另一个配置文件配合使用, 以便在本地计算机上使用邮件存储服务。 用户可能需要使用相应的传输服务在一天中使用相应的传输服务来访问一组邮件系统, 另一组用于当天的其余部分。 配置文件提供了一种灵活的方法来选择邮件系统服务的组合。 
  
配置文件的名称长度最长为64个字母数字字符。 名称可以包含重音字符、下划线和嵌入的空格, 不能包括前导空格或尾随空格。 
  
配置文件按层次结构组织, 分为几个部分, 每个邮件服务一个部分, 服务中的每个服务提供程序一个部分。 相关章节将链接起来, 这样更易于在信息中导航。 每个部分都包含 MAPI 或客户端应用程序用于配置的一系列条目。
  
配置文件中包含的条目因邮件服务和邮件服务而异。 其中一些常见条目包括以下内容:
  
- 每个邮件服务或服务提供商的名称。
    
- 包含服务提供程序和邮件服务的 dll 的名称。
    
- 每个邮件服务的入口点函数的名称。
    
- 组成每个邮件服务的服务提供程序的列表。
    
配置文件可在安装时创建, 在将 MAPI 或邮件服务加载到计算机上时, 或在以后任何时候创建。 MAPI 为配置文件管理提供配置文件向导。 
  
配置文件向导是创建具有最少工作的新配置文件的应用程序。 向导在任何可能的情况下使用默认值设置, 从而节省用户时间和精力。 用户仅在绝对必要时输入值。 有关详细信息, 请参阅[使用配置文件向导创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。 您还可以使用 Office 自定义工具创建新的配置文件。 有关详细信息，请参阅 [Office 自定义工具](https://go.microsoft.com/fwlink/?LinkId=123000)。
  
## <a name="see-also"></a>另请参阅



[MAPI 功能和体系结构](mapi-features-and-architecture.md)

