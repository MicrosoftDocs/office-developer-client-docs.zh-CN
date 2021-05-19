---
title: 实现服务提供程序入口点函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 83ff54c4-86ce-4529-ae45-260dfb763b30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14dd11f873493e32b83dbd1960cac8ff8ef8e436
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332989"
---
# <a name="implementing-a-service-provider-entry-point-function"></a>实现服务提供程序入口点函数

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个服务提供程序 DLL 都有一个入口点函数，MAPI 会调用该函数来加载它。 请注意，此入口点函数与 Win32 DLL 入口点函数 [DllMain](https://msdn.microsoft.com/library/ms682583.aspx)不同。
  
根据提供程序的类型，提供程序入口点函数符合不同的原型。 MAPI 为服务提供商定义不同的入口点函数原型。
  
|**Provider**|**入口点函数原型**|
|:-----|:-----|
|邮件存储提供程序  <br/> |[MSProviderInit](msproviderinit.md) <br/> |
|传输提供程序  <br/> |[XPProviderInit](xpproviderinit.md) <br/> |
|通讯簿提供程序  <br/> |[ABProviderInit](abproviderinit.md) <br/> |
   
这些原型中的许多功能对于所有服务提供程序类型都是相同的。 
  
通讯簿、邮件存储和传输提供程序在入口点功能中执行以下两个主要任务：
  
1. 检查 SPI (接口) 以确保 MAPI 使用的版本与服务提供商使用的版本兼容。 使用包含 MAPI SPI 版本的  _lpulMAPIVer_ 参数和包含 SPI 版本的  _lpulProviderVer_ 参数执行检查。 这些参数是 32 位无符号整数，由三部分组成： 
    
  - 位 24 至 31 表示主要版本。
    
  - 位 16 至 23 表示次要版本。
    
  - 位 0 到 15 表示更新标识符。 尽管主要版本号很少更改，但次要版本号会随着 MAPI 的发布和 SPI 的更改而发生更改。 更新标识符是 Microsoft 内部版本;它用于在开发过程中跟踪更改。 MAPI 定义CURRENT_SPI_VERSION Mapispi.h 头文件中记录的版本常量，以指示当前的 SPI 版本。 如果使用的 SPI MAPI_E_VERSION比 MAPI 使用的版本更新，请对错误检查失败。
    
2. 创建提供程序对象的实例。 由于提供程序可以多次启动和初始化，因此您应每次出现此情况时创建新实例。 提供程序出现在由一个或多个客户端同时使用的多个配置文件中时，或者当提供程序在单个配置文件中多次出现时，提供程序将启动多次。 正如入口点函数原型因提供程序的类型而异一样，提供程序对象的类型也不同。 
    
    如果要编写通讯簿提供程序，请实现 [IABProvider ： IUnknown](iabprovideriunknown.md)。 如果要编写消息存储提供程序，请实现 [IMSProvider ： IUnknown](imsprovideriunknown.md)。 有关详细信息，请参阅 [加载邮件存储提供程序](loading-message-store-providers.md)。
    
    如果要编写传输提供程序，请实现 [IXPProvider ： IUnknown](ixpprovideriunknown.md)。 有关详细信息，请参阅 [初始化传输提供程序](initializing-the-transport-provider.md)。
    
## <a name="see-also"></a>另请参阅



[启动服务提供程序](starting-a-service-provider.md)

