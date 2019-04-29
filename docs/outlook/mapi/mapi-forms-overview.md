---
title: MAPI 表单概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1b3afeaa-4ede-41eb-a3c1-b8947a46ef97
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4e7d48f6f6a47ce28aa0e1291ccef209b998c18e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432518"
---
# <a name="mapi-forms-overview"></a>MAPI 表单概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 表单是邮件的查看器。 每封邮件都有一个消息类, 该邮件类指示用作其查看器的特定表单。 MAPI 定义了几个邮件类, 并实现了用于查看这些类的邮件的窗体。 客户端软件开发者可以创建新的邮件类和自定义表单, 用于查看使用新类创建的邮件。
  
每个自定义表单都实现一组标准菜单命令, 如**Open**、 **Create**、 **Delete**和**Reply**, 以及特定于特定窗体的一组命令。 当窗体处于活动状态时, 某些窗体命令与客户端应用程序的用户界面集成在一起。其他窗体命令完全替换客户端命令。 
  
下图显示了使用表单所涉及的 MAPI 组件之间的关系。 
  
**MAPI 表单体系结构**
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
在该图中, 请注意, 表单管理器扮演的角色与其他 MAPI 服务提供程序类似, 但它不是服务提供商本身。 表单管理器是一个可替换的 DLL, 可实现某些 MAPI 接口。 虽然开发人员可以实施自己的表单管理器, 但大多数环境将使用 Microsoft 提供的表单管理器, 因为表单管理器的复杂性。
  
以下列表介绍了图表中的组件以及它们与其他组件的关系:
  
- 邮件客户端: 可使用表单对象的应用程序。 邮件客户端使用 MAPI 表单接口与表单管理器进行通信, 以便将邮件加载到表单对象中。
    
- mapi 表单接口: 用于在与表单相关的 MAPI 组件之间进行通信的已定义标准。
    
- 表单管理器: 邮件客户端用来处理表单库中的表单安装、表单服务器加载和邮件客户端与表单服务器之间的初始通信的 DLL。
    
- 表单库: 与表单服务器相关联的可执行文件的永久存储。
    
- 表单服务器: 实现表单的可执行文件。 表单服务器创建表单对象和用户界面以处理特定邮件。 此可执行文件也是一台 ole 服务器, 遵循常规的 ole 约定。
    
- 表单对象: 由与特定邮件对应的表单服务器创建的运行时对象。 表单对象在其表单服务器所在的同一个进程上下文中运行。
    
有关 mapi 表单组件的详细信息, 请参阅[mapi 表单](mapi-forms.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

