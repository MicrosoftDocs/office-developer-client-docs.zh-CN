---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 闲/忙 API 允许邮件提供程序为指定的时间范围内的指定用户帐户提供忙/闲状态信息。
ms.openlocfilehash: 1bcd191b57238771ede6f035216fe3997e82e03a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317008"
---
# <a name="about-the-freebusy-api"></a>关于忙/闲 API

闲/忙 API 允许邮件提供程序为指定的时间范围内的指定用户帐户提供忙/闲状态信息。 用户日历上的一段时间的忙/闲状态为以下之一: 外出、忙碌、暂定或免费。
  
## <a name="create-a-freebusy-provider"></a>创建忙/闲提供程序

若要向邮件用户提供忙/闲信息, 邮件提供商将创建一个忙/闲提供商并将其注册到 Outlook。 忙/闲提供程序必须实现以下接口。 请注意, 这些接口中的多个成员不受支持, 必须返回指定的返回值。 特别是, 闲/忙 API 不支持对忙/闲信息的写入访问权限, 并可委派帐户访问权限。
  
- [IFreeBusySupport](ifreebusysupport.md) —此接口支持用于访问指定用户的忙/闲数据的接口的规范。 它使用[FBUser](fbuser.md)来标识用户。 
    
- [IFreeBusyData](ifreebusydata.md) —此接口获取并设置给定用户的时间范围, 并返回用于枚举此时间范围内的忙/闲数据块的接口。 它使用相对于获取和设置此时间范围的相对时间。 有关详细信息, 请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。
    
- [IEnumFBBlock](ienumfbblock.md) —此接口支持在某个时间范围内访问和枚举用户的忙/闲数据块。 
    
   > [!NOTE]
   > 枚举包含用于指示用户日历上某个时间范围内 (由[IFreeBusyData:: EnumBlocks](ifreebusydata-enumblocks.md)) 指定的时间段内的忙/闲状态的忙/闲块。 日历中的项目 (如约会和会议请求) 枚举中的窗体块。 在日历上彼此相邻的项目和具有相同的忙/闲状态的项目组合在一起形成一个单独的块。 日历上的一段空闲时间也会形成一个块。 因此, 枚举中的任何两个连续块都不会具有相同的忙/闲状态。 这些块不会及时重叠。 当日历上有重叠项目时, Outlook 将基于此优先级顺序, 合并这些项目以形成枚举中不重叠的忙/闲块: 外出、忙碌、暂定。 
  
若要在 Outlook 中注册闲/忙提供商, 邮件提供商应执行以下操作:
  
1. 向 COM 注册闲/忙提供程序, 提供一个 CLSID, 以允许访问提供程序对**IFreeBusySupport**的实现。 
    
2. 通过在系统注册表中设置以下项 (其中`<xx.x>`表示 Outlook 的版本), 让 Outlook 知道闲/忙提供程序存在: 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   例如, 如果传输提供程序是 SMTP, 若要向 Microsoft Outlook 2010 注册提供程序, 请将以下注册表项设置为下表中的数据: 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |名称 |类型 |值 |
   |:-----|:-----|:-----|
   |SMTP  |REG_SZ  |{CLSID for IFreeBusySupport 的各个实现}  |
   
   在这种情况下, Outlook 将共同创建 COM 类, 并使用它来检索任何 SMTP 邮件用户的忙/闲信息。
    
若要支持使用 SMTP 之外的地址条目类型的通讯簿和传输提供程序, 请相应地更改*名称*。 
  
> [!NOTE]
> 在安装过程中, 忙/闲提供商应检查是否已存在相同地址条目类型的注册表设置。 如果是这样, 则忙/闲提供程序应覆盖该地址条目类型的当前提供程序, 并在卸载时还原到该提供程序。 但是, 如果用户为同一地址条目类型安装了多个忙/闲提供程序, 则用户应按相反的顺序卸载这些提供程序 (即, 始终卸载最新的提供程序)。 否则, 注册表可能指向已卸载的提供程序。 
  
## <a name="api-components"></a>API 组件

忙/闲 API 包括以下组件:
  
### <a name="definitions"></a>定义

- [常量 (忙/闲 API)](constants-free-busy-api.md)
    
### <a name="data-types"></a>数据类型

- [FBBlock_1](fbblock_1.md)
- [FBStatus](fbstatus.md)
- [FBUser](fbuser.md)
    
### <a name="interfaces"></a>接口

- [IEnumFBBlock](ienumfbblock.md)
- [IFreeBusyData](ifreebusydata.md)
- [IFreeBusySupport](ifreebusysupport.md)
    

