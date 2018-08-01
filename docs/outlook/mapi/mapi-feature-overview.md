---
title: MAPI 功能概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22cf56c5-2804-40a8-99e6-a6d127897720
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ff3677a2bbc8ca54e5bc96ae1e873e3efd3c6bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776225"
---
# <a name="mapi-feature-overview"></a>MAPI 功能概述
 
**适用于**： Outlook 
  
MAPI 有几个重要功能，使其提供的开发人员使用并以无缝方式使用不同邮件系统以一致方式。 这些功能包括一款全面和打开编程接口，并支持的行业标准。 
  
由于 MAPI 是开放的编程接口，它使用户能够添加任何必要的自定义现在和未来的泛型方式提供服务。 MAPI 编程接口满足了具有不同的消息需要，如需要只发送文档的能力的字处理应用程序或工作组需要的应用程序共享的能力的客户端应用程序的要求和存储不同类型的数据。 实际上，任何应用程序需要 exchange 或信息存储在特定格式可以受益从 MAPI 编程接口。 任何服务提供商可以使用接口公开其邮件系统的独特功能选择向应用程序用户提供最大好处这些功能。
  
MAPI 提供了用于前端消息客户端应用程序的编程接口和后端服务提供商使用的编程接口之间分隔。 从服务提供商将客户端界面使单个应用程序以使用多个邮件系统和多个应用程序使用单个服务提供商。 常见的 Microsoft 基于 Windows 的用户界面适用于每个组件。 这是用户很有用。 用户可以从多种系统，具体取决于在任何时候，其需求选择，并可以使用一致每个选定的系统，从而提供从特定的邮件系统，则返回 true 独立性。 
  
例如，单个消息客户端应用程序可以接收来自传真、 语音邮件和 RSS 源的邮件。 从所有这些系统的消息可以放在一个位置或通用收件箱，在到达中。 具有单个应用程序处理所有这些系统可以降低开发、 用户培训和系统管理的成本。 
  
将提供程序接口中的客户端界面中删除任何置于邮件系统，反之亦然的应用程序的编程依赖项。 客户端应用程序和服务提供商的开发人员编写代码以一组标准的 MAPI 功能，而不是多种多样的特定于应用程序或消息系统特定功能。 开发人员关注仅及其组件，它是客户端或服务提供商，是否 MAPI 处理其余，从而减少了开发时间和成本。
  
MAPI 编程接口提供了一组全面的功能。 MAPI 针对在工作组应用程序的强大新市场 — 与传真、 年 12 月一-在-1、 语音邮件和公共 communications 服务，例如在 & T Easylink 服务、 CompuServe 和 MCI 如下不同邮件系统通信的应用程序邮件。 MAPI 界面使服务提供商可供所有这些系统。 
  
MAPI 兼容的对象是在窗体上类似于组件对象模型 (COM) 对象。 COM 对象实现的一组到一个或多个接口所属的方法或相关如何对象的行为和操作 COM 中定义的函数集 用户只能通过指向这些接口访问 COM 对象。
  
MAPI 提供了通过此类作为 SMTP 和 X.400 的行业标准的跨平台支持。 您可以运行在 Windows 7、 Windows Vista、 Windows Server 2008、 Windows Server 2003 和 Windows XP 上的 MAPI 应用程序。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

