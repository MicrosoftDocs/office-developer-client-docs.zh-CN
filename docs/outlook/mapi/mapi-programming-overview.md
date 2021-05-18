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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408339"
---
# <a name="mapi-programming-overview"></a>MAPI 编程概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本 Microsoft Outlook消息传递 API (MAPI) 参考是针对 C 和 C++ 开发人员编写的，具有各种消息传递需求和经验。 对于想要使用 MAPI 扩充其具有邮件功能的应用程序的开发人员，不需要特定的必备知识。 您需要具有邮件和组件对象模型 (COM) 的背景，以使用 MAPI 为专用邮件系统服务创建完整的工作组应用程序或驱动程序。
  
在开始开发工作之前，应考虑以下有关如何使用 MAPI、登录过程以及如何创建和配置配置文件和邮件服务的信息。
  
MAPI 应用程序接口 (MAPI) 是一组广泛的功能，开发人员可以使用这些功能创建启用邮件的应用程序。 完整的函数库称为 MAPI。 MAPI 使用户可以完全控制客户端计算机上的邮件系统、创建和管理邮件、管理客户端邮箱、服务提供商等。
  
> [!NOTE]
> 扩展 MAPI 与 MAPI 相同，在 MAPI 文档中只称为 MAPI。 
  
 **Simple MAPI**
  
简单 MAPI 提供了一组功能，使您能够将基本级别的邮件功能添加到基于 microsoft Windows应用程序。
  
> [!IMPORTANT]
> 简单 MAPI 函数 MAPISendMail 受 Microsoft Outlook 2013 和 Microsoft Outlook 2010。 其他简单 MAPI 函数在 Windows 中已弃Windows。 
  

