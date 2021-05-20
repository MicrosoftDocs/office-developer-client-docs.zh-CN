---
title: 编写自动化客户端
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
# <a name="writing-an-automated-client"></a>编写自动化客户端

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
自动化客户端应用程序是无人参与运行的应用程序，不显示用户界面。
  
 默认情况下，许多 MAPI 接口方法都显示用户界面。 所有这些方法都有允许客户端允许或禁止此显示的标志。 虽然 MAPI 期望服务提供商遵守这些标志，但有些提供程序并不总是符合这些预期要求。 不遵守标志的合法原因是服务提供商依赖于不允许用户界面抑制的另一个服务。 如果要开发自动化客户端，请仔细注意您使用的服务提供商及其配置方式。 不要假定用于禁止用户界面的所有调用都将成功。 
  
自动客户端必须具有必要的信息，以正确配置配置文件中每个邮件服务。 有两种方法在登录时提供配置信息：
  
- 服务提供商可以从配置文件中检索信息。
    
- 服务提供商可以提示用户输入信息。 
    
由于第二个选项对自动化客户端不可用，因此这些客户端必须使用第一个选项。 客户端必须仔细配置其配置文件，以确保此选项始终有效。
  
自动客户端始终在 MAPILogonEx MAPI_NO_MAIL调用中设置 [mapILogonEx](mapilogonex.md) 标记以开始 MAPI 会话。 
  

