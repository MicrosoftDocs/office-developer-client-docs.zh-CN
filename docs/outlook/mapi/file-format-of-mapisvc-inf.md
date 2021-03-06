---
title: MapiSvc.inf 文件格式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: b48eda17-83a8-4dc4-85c8-4ca827d13d25
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 8b7c02f2ac39875021cd183bbb1657514912fe8d
ms.sourcegitcommit: 66e74e39f44dca8c41f97f05528b8f9eb1aaed87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061340"
---
# <a name="file-format-of-mapisvcinf"></a>MapiSvc.inf 文件格式

**适用于**：Outlook 2013 | Outlook 2016 
  
MapiSvc.inf 文件相当于 MAPI 邮件服务配置信息的中央数据库。 MapiSvc.inf 中包含有关工作站上安装的邮件服务信息、有关属于每个邮件服务的服务提供程序信息以及有关 MAPI 子系统的信息。 MapiSvc.inf 是配置文件的主要信息来源。 也就是说，构建新的配置文件或者修改现有配置文件时，将从 MapiSvc.inf 复制每个邮件服务或服务提供程序的相关信息。 
  
MapiSvc.inf 分为链接分层分区：
  
1. 包含适用于所有配置文件的信息的分区。 此分区具有三个部分：
    
   - **[服务]** 分区，用于提供至每个后续邮件服务分区的链接。 
    
   - **[帮助文件映射]** 分区，其中包含有关邮件服务提供的 .HLP 文件的信息。 
    
   - **[默认服务]** 分区，用于列出组成默认安装的邮件服务。 
    
2. 包含适用于单个邮件服务的信息的分区。 这些分区中的条目提供了至后续服务提供程序分区的链接。
    
3. 包含适用于邮件服务中的单个服务提供商的信息的分区。
    
下图所示为典型 MapiSvc.inf 文件的组织形式。 三种邮件服务包括：AB、MsgService 和 MS。 在每个邮件服务中，等号右边的名称为服务的显示名称。 每个邮件服务自己的分区位于链接至一个或多个服务提供程序分区的文件中的其他位置。 属于邮件服务的每个服务提供程序均有一个服务提供程序分区。 AB 和 MS 邮件服务为单一提供程序服务，其中，三个服务提供程序均属于 MsgService 服务。
  
**MapiSvc.inf 文件组织**
  
![MapiSvc.inf 文件组织](media/amapi_30.gif "MapiSvc.inf 文件组织")
  
MAPI 提供了 MapiSvc.inf 文件的框架式版本，其中包含 MAPI 子系统的条目。 每个邮件服务实施程序将添加适合于其服务以及属于其服务的服务提供程序的条目。 某些条目为必须项，其余的则是可选项。 例如，MAPI 要求你指定邮件服务中的每个服务提供程序的名称和路径。 如果没有这些信息，则无法加载它们。
  
你可以在邮件服务分区和/或服务提供程序分区添加必须和可选信息。 添加用于描述邮件服务的信息的位置，取决于服务中的服务提供程序数量。 由于此信息适用于服务中的每个服务提供程序，因此，必须使所有提供程序能够访问它。 将此信息存储到邮件服务分区、首选选项或所有服务提供程序分区中。 存储信息一次以免不必要的复制和同步多个副本。
  
如果邮件服务为单一提供程序服务，请将所有邮件服务信息存储到服务提供程序分区，而不是服务分区。 与访问邮件服务分区相比，访问服务提供程序分区速度更快且更直接。 
  
仅将公用配置数据存储到 MapiSvc.inf 文件中。 专用信息或者需要额外保护的信息（如密码或其他凭据）应包括在此文件中。 相反，选择完全不存储此类信息，或者将其作为安全属性存储在配置文件中。 安全属性具有内置的保护功能，如加密。
  
## <a name="reference"></a>参考

若要详细了解如何在 MAPI 阻止提供商 DLL 时排除故障，请参阅 [如何允许 MAPI 加载未注册的提供商 DLL，](https://support.microsoft.com/topic/how-to-allow-mapi-to-load-unregistered-provider-dlls-18d9a1cd-d3d7-fa10-473e-5dfd62d38b0d)。

