---
title: MAPI 功能概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22cf56c5-2804-40a8-99e6-a6d127897720
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b1087f5156ad79b20eb31ef55c0388ffd82e1601
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416921"
---
# <a name="mapi-feature-overview"></a>MAPI 功能概述
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 具有几个关键功能，使开发人员能够无缝地使用和使用不同的邮件系统。 这些功能包括全面、开放的编程接口，并支持行业标准。 
  
由于 MAPI 是一个开放的编程接口，因此它以通用方式提供服务，使用户能够现在和将来添加任何必需的自定义项。 MAPI 编程接口满足具有不同消息需求的客户端应用程序的要求，例如，只需能够发送文档的字处理应用程序，或需要共享和存储不同类型的数据的工作组应用程序。 事实上，任何需要交换或存储特定格式的信息的应用程序都可以从 MAPI 编程接口中获益。 任何服务提供商都可以使用该接口来公开其邮件系统的独特功能，同时选择为应用程序用户提供最大好处的功能。
  
MAPI 在前端邮件客户端应用程序使用的编程接口和后端服务提供商使用的编程接口之间分离。 将客户端接口与服务提供商分离使单个应用程序可以使用多个邮件系统和多个应用程序来使用单个服务提供商。 每个组件都适用于常见的基于 Microsoft Windows用户界面。 这对用户是一大好处。 用户可以从各种系统中选择，具体取决于他们随时的需求，并且可以与每个选定的系统一致地工作，从而提供与特定邮件系统的真正独立。 
  
例如，单个邮件客户端应用程序可以接收来自传真、语音邮件和 RSS 源的邮件。 到达时，来自所有这些系统的邮件都可以放置在单个位置或通用收件箱中。 让单个应用程序处理所有这些系统可减少开发、用户培训和系统管理的成本。 
  
将客户端接口与提供程序接口分离可删除邮件系统对应用程序的任何编程依赖关系，反之亦然。 客户端应用程序和服务提供商的开发人员将代码写入一组标准 MAPI 功能，而不是一组不同的特定于应用程序或特定于邮件系统的功能。 开发人员只关注其组件（无论是客户端还是服务提供商）而 MAPI 处理其余组件，从而减少了开发时间和成本。
  
MAPI 编程接口提供了一组全面的功能。 MAPI 的目标是工作组应用程序的强大新市场 — 与诸如传真、DEC All-In-1、语音邮件和公共通信服务（如 AT&T Easylink Services、CompuServe 和 MCI MAIL）等不同邮件系统通信的应用程序。 MAPI 接口使服务提供商可用于所有这些系统。 
  
MAPI 兼容对象在形式上类似于组件对象模型 (COM) 对象。 COM 对象实现一组属于一个或多个接口的方法，或一组定义对象在 COM 中的行为和运行方式的相关函数。 用户仅通过指向这些接口的指针访问 COM 对象。
  
MAPI 通过诸如 SMTP 和 X.400 等行业标准提供跨平台支持。 您可以在 Windows 7、Windows Vista、Windows Server 2008、Windows Server 2003 和 Windows XP 上运行 MAPI 应用程序。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

