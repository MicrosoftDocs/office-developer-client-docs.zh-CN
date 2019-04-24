---
title: 测试和调试
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0afceb1f-9086-4cc9-8ce4-fb9256a81a9c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8e1f15ae354894aede4e8418e6428d0524ccb70d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316480"
---
# <a name="testing-and-debugging"></a>测试和调试

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
测试策略将根据您是否在开发客户端或服务提供程序而有所不同。 由于客户端应用程序需要一个或多个服务提供程序才能运行, 因此应在具有不同的服务提供程序集的环境中测试客户端。
  
但是, 服务提供程序应在与其他提供程序集成之前在隔离中进行测试。 MAPI 提供的工具旨在测试特定类型的服务提供程序的功能。 [MFCMAPI](https://go.microsoft.com/fwlink/?LinkId=124154)示例应用程序演示如何测试通讯簿提供程序的功能, 以及如何与邮件存储提供程序一起使用。 
  
## <a name="see-also"></a>另请参阅



[MAPI 编程概述](mapi-programming-overview.md)
  
[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

