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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341711"
---
# <a name="starting-a-service-provider"></a>启动服务提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在客户端启动与 MAPI 的会话之后, 在某个时间点将启动服务提供程序。 当客户端请求服务时, 将启动传输提供程序。 通讯簿和邮件存储提供程序在客户端登录过程中启动。
  
客户端调用[IMAPISession:: OpenAddressBook](imapisession-openaddressbook.md)以加载配置文件中包含的每个通讯簿提供程序, 并使用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)加载特定的邮件存储提供程序。 作为邮件服务一部分的通讯簿提供程序在服务中的任何其他提供程序之前启动。 
  
MAPI 通过执行以下操作来启动活动配置文件中的每个服务提供程序:
  
- 在配置文件中查找其 DLL 的名称。 您需要在 mapisvc.inf 配置文件中注册提供程序 DLL 的名称, 以确保它出现在配置文件中。 将服务提供程序添加到配置文件时 (单独或作为邮件服务的一部分), 所有 **[服务提供程序]** 从适用于您的提供程序的 mapisvc.inf 部分将复制到配置文件中。 有关 mapisvc.inf 结构的详细信息, 请参阅[mapisvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。
    
- 调用 Windows API 函数**LoadLibrary**以加载 DLL。 由于 MAPI 会在每次使用服务提供程序 DLL 时 (无论是否已加载) 或仅在首次使用服务提供程序 DLL 时调用**LoadLibrary** , 因此服务提供程序不一定会对其加载次数做出假设。 对于每个**LoadLibrary**调用, MAPI 会在不再需要服务提供程序 DLL 时调用 Windows API 函数**FreeLibrary** 。 
    
- 调用提供程序的入口点函数。 MAPI 调用提供程序的入口点函数来启动登录过程。 入口点函数确保您使用的服务提供程序接口 (SPI) 版本与 MAPI 所使用的版本兼容。 这些函数还返回指向新创建的提供程序对象的指针。 有关为提供程序创建入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

