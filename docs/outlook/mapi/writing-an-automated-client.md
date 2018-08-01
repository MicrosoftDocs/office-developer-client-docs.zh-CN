---
title: 编写自动化客户端
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8f9ac1a-b377-4f83-8fb6-ed85ab9053d0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e5357c1e822dda35d3f38e00f91b58adbaf0ff9d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779094"
---
# <a name="writing-an-automated-client"></a>编写自动化客户端

  
  
**适用于**： Outlook 
  
自动客户端应用程序是运行无人参与，不显示用户界面的应用程序。
  
 默认情况下，许多 MAPI 接口方法显示用户界面。 所有这些方法具有允许客户端，以允许或禁止此显示的标志。 尽管 MAPI 预计服务提供商接受这些标志，有一些始终不满足这些期望的提供程序。 不考虑标志的合法原因是服务提供程序，依赖于另一个不允许用户界面禁止显示的服务。 如果要开发的自动客户端，请务必注意您使用的服务提供程序和配置方式。 不要假定所有呼叫禁止在用户界面将会成功。 
  
自动客户端必须具有所需的信息适用于每一个消息服务的正确配置配置文件中。 有两种方式以提供登录时的配置信息：
  
- 服务提供商可以从配置文件中检索信息。
    
- 服务提供商可以提示用户输入的信息。 
    
向自动化客户端，第二个选项不可用，因为这些客户端必须使用第一个选项。 客户端必须配置其配置文件仔细以确保始终此选项。
  
自动客户端始终[MAPILogonEx](mapilogonex.md)函数调用开始 MAPI 会话中设置 MAPI_NO_MAIL 标志。 
  

