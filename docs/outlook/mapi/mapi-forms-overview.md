---
title: MAPI 表单概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1b3afeaa-4ede-41eb-a3c1-b8947a46ef97
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 91bc0641723a92d8dc86bf3d1037d8e9936930ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776247"
---
# <a name="mapi-forms-overview"></a>MAPI 表单概述
  
**适用于**： Outlook 
  
MAPI 表单是邮件查看器。 每个邮件有规定用作其查看器的特定窗体的邮件类。 MAPI 定义多个邮件类，并已实现查看这些类的邮件的表单。 客户端软件开发人员可以创建新的邮件类和查看邮件使用的新类创建的自定义表单。
  
每个自定义窗体实现一组标准菜单命令，如**打开**、**创建**、**删除**和**答复**和一组特定于特定的窗体的命令。 窗体命令的一些集成在一起的客户端应用程序的用户界面窗体处于活动状态; 时其他窗体命令完全替换客户端命令。 
  
下图显示了使用窗体所涉及的 MAPI 组件之间的关系。 
  
**MAPI 表单体系结构**
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
在图表中，请注意窗体管理器播放尽管这不是本身的服务提供商类似于其他 MAPI 服务提供商的角色。 窗体管理器是实现一些 MAPI 接口可替换 DLL。 开发人员可以实现自己的窗体管理器，尽管大多数环境中将使用由 Microsoft 提供的由于窗体管理器的复杂性的窗体管理器。
  
以下列表描述中图表及其关系，以及其他组件的组件：
  
- 消息客户端： 的应用程序可以使用窗体对象。 消息客户端使用的 MAPI 表单接口与窗体管理器加载到表单对象的消息进行通信。
    
- MAPI 表单接口： 与窗体相关的 MAPI 组件之间的通信已定义的标准。
    
- 窗体管理器： 用于处理安装的表单库中的窗体、 窗体服务器和消息客户端与窗体服务器之间的初始通信的加载消息客户端的 DLL。
    
- 表单库： 永久存储与窗体服务器关联的可执行文件。
    
- 表单服务器： 实现的窗体的可执行文件。 窗体服务器创建窗体对象和处理特定邮件的用户界面。 此可执行文件也是 OLE 服务器，并且符合您的常用 OLE 约定。
    
- 窗体对象： 创建窗体服务器对应于特定邮件的运行时对象。 作为其窗体服务器的相同过程上下文中运行窗体对象。
    
有关 MAPI 表单组件的详细信息，请参阅[MAPI Forms](mapi-forms.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

