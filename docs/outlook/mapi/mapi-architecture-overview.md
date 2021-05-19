---
title: MAPI 体系结构概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00d2993c-d66a-4a00-9fb2-98696d29a007
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98a723528a714918ad7e0f10534efb0d38ef139a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410075"
---
# <a name="mapi-architecture-overview"></a>MAPI 体系结构概述
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义模块体系结构，如下图所示。  
  
![Outlook 2010 体系结构](media/amapi_43.gif "Outlook 2010 体系结构")
  
MAPI 应用程序称为客户端应用程序，因为它是 MAPI 子系统的客户端。 基于邮件的应用程序将邮件用作其处理的中心部分，并提供广泛的邮件功能，例如交换各种格式的各种类型的信息以及在本地保存和组织信息的能力。 电子邮件、计划和工作流程应用程序是基于邮件的应用程序的示例。
  
MAPI 子系统由常见的用户界面和编程接口组成。 常见的用户界面是一组对话框，这些对话框使客户端应用程序具有一致的外观，并且用户可以一致地工作。
  
MAPI 具有由 MAPI 子系统、客户端软件开发人员和服务提供商开发人员使用的编程接口。 MAPI 编程接口是基于对象的主要编程接口。 MAPI 编程接口类似于 OLE 组件对象模型，由用 C 或 C++ 编写的 MAPI 子系统和基于消息的客户端应用程序使用。 
  
作为客户端软件开发人员，您直接通过 MAPI 编程接口进行 MAPI 调用。 可以使用单个 MAPI 客户端接口或接口组合来实现消息传递。 单个应用程序可以调用属于任何接口的方法或函数。
  
## <a name="see-also"></a>另请参阅

-[MAPI 功能和体系结构](mapi-features-and-architecture.md)

