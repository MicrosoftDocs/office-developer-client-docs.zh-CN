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
  
每个服务提供程序 DLL 都有一个入口点函数, MAPI 调用它来加载它。 请注意, 此入口点函数与[DllMain](https://msdn.microsoft.com/library/ms682583.aspx)(Win32 DLL 入口点函数) 不同。
  
根据提供程序的类型, 提供程序入口点函数符合不同的原型。 MAPI 为服务提供程序定义了不同的入口点函数原型。
  
|**Provider**|**入口点函数原型**|
|:-----|:-----|
|邮件存储区提供程序  <br/> |[MSProviderInit](msproviderinit.md) <br/> |
|传输提供程序  <br/> |[XPProviderInit](xpproviderinit.md) <br/> |
|通讯簿提供程序  <br/> |[ABProviderInit](abproviderinit.md) <br/> |
   
对于所有服务提供程序类型, 这些原型中的许多功能都是相同的。 
  
通讯簿、邮件存储和传输提供程序在其入口点函数中执行以下两个主要任务:
  
1. 检查服务提供程序接口 (SPI) 的版本, 确保 MAPI 使用的版本与您的服务提供商使用的版本兼容。 使用包含 MAPI SPI 版本的_lpulMAPIVer_参数以及包含 SPI 版本的_lpulProviderVer_参数, 以执行检查。 这些参数是由三部分组成的32位无符号整数: 
    
  - 24到31位代表主要版本。
    
  - 16到23位代表次要版本。
    
  - 0到15位表示更新标识符。 尽管主要版本号很少更改, 但每当 MAPI 发布且 SPI 发生更改时, 次要版本号都会发生变化。 更新标识符是 Microsoft 内部内部版本;它用于跟踪在开发过程中所做的更改。 MAPI 定义在 Mapispi 头文件中记录的 CURRENT_SPI_VERSION 常量, 以指示目前的 SPI 版本。 如果您使用的 SPI 版本比 MAPI 使用的版本新, 则您的检查会失败, 并出现错误 MAPI_E_VERSION。
    
2. 创建提供程序对象的实例。 由于您的提供程序可以多次启动和初始化, 因此在每次发生此情况时应创建一个新实例。 当提供程序出现在多个配置文件中时, 它们会在同时由一个或多个客户端使用, 或者当它们在一个配置文件中多次出现时多次启动。 正如提供程序的类型不同, 入口点函数原型的不同之处在于提供程序对象的类型。 
    
    如果要编写通讯簿提供程序, 请实施[IABProvider: IUnknown](iabprovideriunknown.md)。 如果要编写邮件存储区提供程序, 请实现[IMSProvider: IUnknown](imsprovideriunknown.md)。 有关详细信息, 请参阅[加载邮件存储提供程序](loading-message-store-providers.md)。
    
    如果要编写传输提供程序, 请实施[IXPProvider: IUnknown](ixpprovideriunknown.md)。 有关详细信息, 请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。
    
## <a name="see-also"></a>另请参阅



[启动服务提供程序](starting-a-service-provider.md)

