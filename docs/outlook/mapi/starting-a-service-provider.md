---
title: 启动服务提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4b61cc3-d9fe-4616-a05c-d1e4096b5abd
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: d14a9961002d63733423af474e147ec5001051fb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586331"
---
# <a name="starting-a-service-provider"></a>启动服务提供程序

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在某些点客户端的 MAPI，启动会话后将启动服务提供商。 当客户端请求其服务已启动传输提供程序。 地址簿和消息存储提供程序已启动客户端的登录过程。
  
在客户端调用[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)加载通讯簿提供程序的配置文件和[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)加载特定的邮件存储提供程序中包含的每个。 通讯簿提供程序的一部分的消息服务已启动之前的任何服务中的其他提供程序。 
  
MAPI 启动每个服务提供商活动配置文件中执行以下操作：
  
- 配置文件中查找其 DLL 的名称。 您所需的 Mapisvc.inf 配置文件，以确保它显示在配置文件中注册的提供程序 DLL 名称。 服务提供商添加到配置文件，分别或作为消息服务的一部分时, 的所有 **[服务提供商]** 部分从 Mapisvc.inf 适用于您的提供商的复制到配置文件。 有关 Mapisvc.inf 结构的详细信息，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。
    
- 调用 Windows API 函数**LoadLibrary**加载 DLL。 由于 MAPI 调用**LoadLibrary**一种每次它使用 （无论是否它已加载） 服务提供程序 DLL 或只在首次，服务提供商必须进行假设将加载的次数。 **LoadLibrary**每次调用，MAPI 调用 Windows API 函数**句**时不再需要 DLL 的服务提供商。 
    
- 为提供程序调用入口点函数。 MAPI 呼叫提供商的入口点函数启动登录过程。 入口点函数确保您使用的服务提供程序接口 (SPI) 正在使用 MAPI 的版本与之兼容的版本。 这些函数还返回到新创建提供商对象的指针。 有关创建一个条目的详细信息指向函数提供程序，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

