---
title: MAPI 编程概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30ac637a-874f-4660-b5d0-d28d69486f64
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: d69d15f0f635c81bea30401b3a6d6e3ccf620112
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328271"
---
# <a name="mapi-programming-overview"></a>MAPI 编程概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此 Microsoft Outlook 消息处理 API (MAPI) 引用是为 c 和 c + + 开发人员编写的, 其中包含针对消息传递的各种需求和体验。 对于想要使用 MAPI 来扩充其具有邮件功能的应用程序的开发人员, 不需要特定的先决条件知识。 您需要在消息传递中有背景, 组件对象模型 (COM) 才能使用 MAPI 为专用邮件系统服务创建完全规模的工作组应用程序或驱动程序。
  
在开始开发工作之前, 应考虑以下有关如何使用 MAPI、登录过程以及如何创建和配置配置文件和邮件服务的信息的信息。
  
邮件应用程序接口 (MAPI) 是一组广泛的功能, 开发人员可使用这些函数创建启用邮件功能的应用程序。 完整的函数库称为 MAPI。 MAPI 支持对客户端计算机上的邮件系统进行完全控制、创建和管理邮件、管理客户端邮箱、服务提供商等。
  
> [!NOTE]
> 扩展 mapi 与 mapi 相同, 并在 mapi 文档中简称为 mapi。 
  
 **Simple MAPI**
  
简单 MAPI 提供了一组功能, 使您能够向基于 Microsoft Windows 的应用程序中添加基本的邮件功能级别。
  
> [!IMPORTANT]
> microsoft outlook 2013 和 microsoft outlook 2010 支持简单 MAPI 函数 MAPISendMail。 Windows 中已弃用其他简单 MAPI 函数。 
  

