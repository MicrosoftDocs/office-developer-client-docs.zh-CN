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
ms.openlocfilehash: 40bbe110c7453cf2360fc103710fbc3bcb7f1c67
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572051"
---
# <a name="implementing-a-service-provider-entry-point-function"></a>实现服务提供程序入口点函数

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
每个服务提供商 DLL 有入口点 MAPI 调用以将其加载的函数。 请注意此入口点函数不是[DllMain](http://msdn.microsoft.com/en-us/library/ms682583.aspx)，Win32 DLL 入口点函数相同。
  
根据您的提供程序的类型，您的提供程序入口点函数符合不同原型。 MAPI 服务提供程序定义不同的入口点函数原型。
  
|**Provider**|**入口点函数原型**|
|:-----|:-----|
|消息存储提供程序  <br/> |[MSProviderInit](msproviderinit.md) <br/> |
|传输提供程序  <br/> |[XPProviderInit](xpproviderinit.md) <br/> |
|通讯簿提供程序  <br/> |[ABProviderInit](abproviderinit.md) <br/> |
   
大部分中这些原型是功能的相同的所有服务提供程序类型。 
  
通讯簿、 消息存储和传输提供程序执行其入口点函数中的以下两个主要任务：
  
1. 检查服务提供程序接口 (SPI) 以确保 MAPI 用版本与服务提供商使用的版本兼容的版本。 使用_lpulMAPIVer_参数，其中包含的 MAPI SPI 版本和_lpulProviderVer_参数，其中包含您 SPI 版本，以执行检查。 这些参数是 32 位无符号的整数三部分组成： 
    
  - 通过 31 的 24 位表示的主要版本。
    
  - 通过 23 16 位表示的次要版本。
    
  - 0 到 15 位表示更新标识符。 尽管很少更改的主版本号，次要版本号更改每当发布 MAPI 和 SPI 已更改。 更新标识符是 Microsoft 内部版本号它用于跟踪在开发过程中的更改。 MAPI 定义 CURRENT_SPI_VERSION 常量，记录在 Mapispi.h 标头文件，以指示存在 SPI 版本。 如果使用的版本比使用 MAPI 的版本更新 SPI，失败错误 MAPI_E_VERSION 您检查。
    
2. 创建提供商对象的实例。 因为您的提供商可以启动和初始化多次，应发生这种情况每次创建的新实例。 提供程序已启动多次时显示在一个或多个客户端，同时使用中的多个配置文件或者多次出现一个配置文件中。 仅当入口点函数原型不同，具体取决于您的提供程序的类型，也提供商对象的类型。 
    
    如果您正在编写通讯簿提供程序，实现[IABProvider: IUnknown](iabprovideriunknown.md)。 如果您正在编写消息存储提供程序，实现[IMSProvider: IUnknown](imsprovideriunknown.md)。 有关详细信息，请参阅[加载消息存储提供程序](loading-message-store-providers.md)。
    
    如果您正在编写传输提供程序，实现[IXPProvider: IUnknown](ixpprovideriunknown.md)。 有关详细信息，请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。
    
## <a name="see-also"></a>另请参阅



[启动服务提供程序](starting-a-service-provider.md)

