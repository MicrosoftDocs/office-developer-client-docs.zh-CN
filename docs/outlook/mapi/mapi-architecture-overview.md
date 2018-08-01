---
title: MAPI 体系结构概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00d2993c-d66a-4a00-9fb2-98696d29a007
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db8ca0945c429e7b277ec95b419386d1ce175169
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776189"
---
# <a name="mapi-architecture-overview"></a>MAPI 体系结构概述
 
**适用于**： Outlook 
  
MAPI 定义的模块化体系结构，如下图所示。  
  
![Outlook 2010 体系结构](media/amapi_43.gif "Outlook 2010 体系结构")
  
MAPI 应用程序被称为客户端应用程序，因为它是 MAPI 子系统的客户端。 基于消息的应用程序采用消息为其处理的核心部分，并提供大量的消息功能，如的各种格式和功能中保存和组织的信息本地的各种类型的信息交换。 电子邮件、 日程安排和工作流应用程序基于消息的应用程序的示例。
  
MAPI 子系统通用的用户界面和编程接口组成。 常见用户界面是一致的外观和用户为客户端应用程序提供了一套对话框以一致方式工作。
  
MAPI 具有编程通过 MAPI 子系统、 客户端软件开发人员，以及服务提供程序开发人员使用的接口。 MAPI 编程接口是主要基于对象的编程接口。 MAPI 编程接口类似于 OLE 组件对象模型和 MAPI 子系统和基于消息的客户端应用程序编写 C 或 c + + 中使用。 
  
作为客户端软件开发人员，您可以直接通过 MAPI 编程界面发起 MAPI 呼叫。 您可以实现消息的单个 MAPI 客户端界面或接口的组合。 单个应用程序可以发起呼叫到方法或属于任何接口的函数。
  
## <a name="see-also"></a>另请参阅

-[MAPI 功能和体系结构](mapi-features-and-architecture.md)

