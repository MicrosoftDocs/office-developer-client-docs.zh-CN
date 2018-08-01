---
title: MAPI 配置文件概述 （英文)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d6c57be6-2397-4ab1-a912-028454dffc44
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 573709c4374786bb1bd3d763c8ba91de59f7fb1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776274"
---
# <a name="mapi-profile-overview"></a>MAPI 配置文件概述 （英文)

  
  
**适用于**： Outlook 
  
一个配置文件信息的消息服务和客户端应用程序的用户希望可在特定的 MAPI 会话过程中的服务提供商的集合。 每个用户都至少一个配置文件;许多用户仍使用原来多个。 例如，用户可能具有一个配置文件以使用基于服务器的消息存储服务和另一个配置文件以在本地计算机上处理的消息存储服务。 用户可能需要访问一组消息系统使用某一天和另一天中的 rest 设置的一部分的合适的传输服务。 配置文件提供灵活的方式选择的消息系统服务的组合。 
  
配置文件可以在长度具有最 64 字母数字字符的名称。 名称可以包括重音字符、 下划线和嵌入的空格，并且不能包含前导或尾随空格。 
  
配置文件的分层组织和分为部分，为每个消息服务的一部分与服务中的每个服务提供商的一节。 链接的相关的章节，从而方便信息中导航。 每个部分包含一系列配置使用 MAPI 或客户端应用程序的条目。
  
配置文件中包含的项因消息服务的邮件服务。 以下一些常见的条目：
  
- 每个邮件服务或服务提供商的名称。
    
- 包含服务提供商和消息服务的 Dll 名称。
    
- 每个消息服务的入口点函数的名称。
    
- 组成每个邮件服务服务提供商的列表。
    
在安装时，当 MAPI 或消息服务加载到计算机上，或任何更高版本时，可以创建配置文件。 MAPI 提供配置文件管理配置文件向导。 
  
配置文件向导是工作的应用程序创建新配置文件具有最少。 向导将使用默认值的设置，尽可能保存用户时间和精力。 用户输入值仅在绝对需要时。 有关详细信息，请参阅[创建使用配置文件向导配置文件](creating-a-profile-by-using-the-profile-wizard.md)。 您可以使用 Office 自定义工具以创建新的配置文件。 有关详细信息，请参阅[Office Customization Tool](http://go.microsoft.com/fwlink/?LinkId=123000)。
  
## <a name="see-also"></a>另请参阅



[MAPI 功能和体系结构](mapi-features-and-architecture.md)

