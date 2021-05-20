---
title: 启动服务提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4b61cc3-d9fe-4616-a05c-d1e4096b5abd
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: f67976681ef0283c86e1c09c49e531572668ff50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439553"
---
# <a name="starting-a-service-provider"></a>启动服务提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在客户端使用 MAPI 启动会话后的某一时间点，将启动您的服务提供商。 当客户端请求其服务时，将启动传输提供程序。 通讯簿和邮件存储提供程序在客户端的登录过程中启动。
  
客户端调用 [IMAPISession：：OpenAddressBook](imapisession-openaddressbook.md) 以加载配置文件中包含的每个通讯簿提供程序和 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 以加载特定的邮件存储提供程序。 作为邮件服务的一部分的通讯簿提供程序在服务中的其他任何提供程序之前启动。 
  
MAPI 通过执行以下操作来启动活动配置文件中的每个服务提供程序：
  
- 在配置文件中定位 DLL 的名称。 您必须在 Mapisvc.inf 配置文件中注册提供程序 DLL 的名称，以确保该名称出现在配置文件中。 将服务提供程序添加到配置文件（无论是单独添加还是作为邮件服务的一部分）时，Mapisvc.inf 中适用于您的提供程序的所有 **[Service Provider]** 部分将复制到配置文件中。 有关 Mapisvc.inf 结构详细信息，请参阅 [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md)。
    
- 调用 Windows API 函数 **LoadLibrary** 以加载 DLL。 由于 MAPI 每次使用服务提供程序 DLL (都会调用 **LoadLibrary，** 而无论它是已加载) 还是仅在第一次加载，因此您的服务提供商不得假设将加载它的时间。 每次调用 **LoadLibrary** 时，MAPI 都会调用 Windows API 函数 **FreeLibrary（** 当不再需要服务提供程序 DLL 时）。 
    
- 调用提供程序的入口点函数。 MAPI 调用提供程序的入口点函数以启动登录过程。 入口点函数确保您使用的是与 MAPI (版本兼容的 SPI) 接口版本。 这些函数还会返回指向新创建的提供程序对象的指针。 有关为提供程序创建入口点函数的信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

