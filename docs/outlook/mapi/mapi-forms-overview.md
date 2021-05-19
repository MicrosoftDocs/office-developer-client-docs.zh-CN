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
  
MAPI 窗体是邮件的查看器。 每封邮件都有一个消息类，用于指示用作其查看器的特定窗体。 MAPI 定义多个邮件类，并且已实现用于查看这些类的消息的表单。 客户端软件开发人员可以创建新的邮件类和自定义窗体，以便查看使用新类创建的消息。
  
每个自定义窗体都实现一组标准菜单命令，如 **"** 打开"、**创建**、删除和答复，以及一组特定于特定窗体的命令。 当表单处于活动状态时，某些表单命令会与客户端应用程序的用户界面集成;其他表单命令完全替换客户端命令。 
  
下图显示了使用表单所涉及的 MAPI 组件之间的关系。 
  
**MAPI 表单体系结构**
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
在图中，请注意，表单管理器扮演的角色与其他 MAPI 服务提供程序相似，尽管它本身不是服务提供商。 表单管理器是一个可替换的 DLL，它实现了一些 MAPI 接口。 尽管开发人员可以实施自己的表单管理器，但由于表单管理器的复杂性，大多数环境都将使用 Microsoft 提供的表单管理器。
  
以下列表描述了图表中的组件及其与其他组件的关系：
  
- 邮件客户端：可以使用表单对象的应用程序。 邮件客户端使用 MAPI 表单接口与表单管理器进行通信，以将邮件加载到表单对象中。
    
- MAPI 表单接口：MAPI 组件之间与表单相关的通信的定义标准。
    
- 表单管理器：邮件客户端用于处理表单库中表单的安装、表单服务器的加载以及邮件客户端和表单服务器之间的初始通信的 DLL。
    
- 表单库：与表单服务器关联的可执行文件的永久存储。
    
- 表单服务器：实现表单的可执行文件。 表单服务器创建表单对象和用户界面来处理特定消息。 此可执行文件也是 OLE 服务器，并且遵循常用的 OLE 约定。
    
- Form 对象：由与特定邮件对应的表单服务器创建的运行时对象。 Form 对象与表单服务器在同一进程上下文中运行。
    
有关 MAPI 表单组件详细信息，请参阅 [MAPI Forms](mapi-forms.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

