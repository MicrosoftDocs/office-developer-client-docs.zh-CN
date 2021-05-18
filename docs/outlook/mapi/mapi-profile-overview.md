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
  
配置文件是有关特定 MAPI 会话期间客户端应用程序用户希望其可用的邮件服务和服务提供程序的信息集合。 每个用户都至少有一个配置文件;许多用户保留多个。 例如，用户可能有一个配置文件用于基于服务器的邮件存储服务，另一个配置文件用于本地计算机上的邮件存储服务。 用户可能想要通过使用一天中的相应传输服务访问一组邮件系统，在一天中的其余时间使用另一组传输服务。 配置文件提供了选择邮件系统服务组合的灵活方法。 
  
配置文件的名称长度最多为 64 个字母数字字符。 名称可以包括重音字符、下划线和嵌入空格，并且不能包含前导空格或尾随空格。 
  
配置文件按层次结构组织并分为若干部分，每个邮件服务有一个部分，服务中的每个服务提供商有一个分区。 相关部分链接在一起，便于在信息中导航。 每个部分都包含 MAPI 或客户端应用程序用于配置的一系列条目。
  
配置文件中包含的条目因邮件服务而异。 一些常见条目包括：
  
- 每个邮件服务或服务提供商的名称。
    
- 包含服务提供程序和消息服务的 DLL 的名称。
    
- 每个邮件服务的入口点函数的名称。
    
- 包含每个邮件服务的服务提供商的列表。
    
可以在安装时、将 MAPI 或邮件服务加载到计算机上时或在以后的任何时间创建配置文件。 MAPI 提供配置文件向导以用于配置文件管理。 
  
配置文件向导是一个应用程序，它以最少的工作创建新配置文件。 向导尽可能使用设置的默认值，从而节省用户时间和精力。 用户仅在绝对必要时输入值。 有关详细信息，请参阅 [使用配置文件向导创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。 您还可以使用自定义Office工具创建新配置文件。 有关详细信息，请参阅 [Office 自定义工具](https://go.microsoft.com/fwlink/?LinkId=123000)。
  
## <a name="see-also"></a>另请参阅



[MAPI 功能和体系结构](mapi-features-and-architecture.md)

