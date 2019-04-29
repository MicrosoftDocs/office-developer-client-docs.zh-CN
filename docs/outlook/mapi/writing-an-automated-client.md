---
title: 编写自动客户端
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8f9ac1a-b377-4f83-8fb6-ed85ab9053d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f9ce3452bbc2d3297cc67168835a9387235746a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439763"
---
# <a name="writing-an-automated-client"></a>编写自动客户端

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
自动客户端应用程序是无人值守运行的应用程序, 不显示用户界面。
  
 默认情况下, 许多 MAPI 接口方法显示一个用户界面。 所有这些方法都有标志, 这些标志允许客户端允许或禁止显示此显示。 虽然 MAPI 要求服务提供商服从这些标志, 但有些提供程序并不总是符合这些要求。 不考虑这些标志的合理原因是, 服务提供商对另一项服务的依赖不允许用户界面抑制。 如果要开发自动客户端, 请注意您正在使用的服务提供商以及它们的配置方式。 请勿假定所有调用以禁止用户界面都将成功。 
  
自动客户端必须具有可用于正确配置配置文件中的每个邮件服务的必要信息。 登录时提供了两种提供配置信息的方法:
  
- 服务提供程序可以从配置文件中检索信息。
    
- 服务提供商可以提示用户输入信息。 
    
由于第二个选项对自动客户端不可用, 因此这些客户端必须使用第一个选项。 客户端必须仔细配置其配置文件, 以确保此选项始终有效。
  
自动客户端总是在[MAPILogonEx](mapilogonex.md)函数调用中设置 MAPI_NO_MAIL 标志以开始 MAPI 会话。 
  

