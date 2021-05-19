---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 忙/闲 API 允许邮件提供程序提供指定时间范围内指定用户帐户的忙/闲状态信息。
ms.openlocfilehash: 1bcd191b57238771ede6f035216fe3997e82e03a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433757"
---
# <a name="about-the-freebusy-api"></a>关于忙/闲 API

忙/闲 API 允许邮件提供程序提供指定时间范围内指定用户帐户的忙/闲状态信息。 用户日历上某一个时间块的忙/闲状态如下：外出、忙碌、暂定或空闲。
  
## <a name="create-a-freebusy-provider"></a>创建忙/闲提供程序

为了向邮件用户提供忙/闲信息，邮件提供程序会创建一个忙/闲提供程序，并注册Outlook。 忙/闲提供程序必须实现以下接口。 请注意，这些接口中的许多成员不受支持，必须返回指定的返回值。 特别是，忙/闲 API 不支持对忙/闲信息的写访问和委派对帐户的访问权限。
  
- [IFreeBusySupport](ifreebusysupport.md) - 此接口支持指定接口，这些接口访问指定用户的忙/闲数据。 它使用 [FBUser](fbuser.md) 标识用户。 
    
- [IFreeBusyData](ifreebusydata.md) - 此接口获取和设置给定用户的一个时间范围，并返回用于枚举此时间范围内的忙/闲数据块的接口。 它使用相对时间获取和设置此时间范围。 有关详细信息，请参阅使用 [相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。
    
- [IEnumFBBlock](ienumfbblock.md) - 此接口支持在一个时间范围内访问和枚举用户的忙/闲数据块。 
    
   > [!NOTE]
   > 枚举包含指示用户日历上时间段的忙/闲状态（在 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) (指定的时间范围内）的忙/闲) 。 枚举中的日历项目（如约会和会议请求）表单块。 日历上彼此相邻且具有相同的忙/闲状态的项目组合在一起形成一个块。 日历上的空闲时段也会形成一个块。 因此，枚举中的两个连续块不会具有相同的忙/闲状态。 这些块不会在时间上重叠。 当日历上存在重叠项目时，Outlook合并这些项目以基于以下优先顺序在枚举中形成非重叠的忙/闲块：外出、忙碌、暂定。 
  
若要向用户注册忙/Outlook，邮件提供程序应执行以下操作：
  
1. 使用 COM 注册忙/闲提供程序，提供允许访问提供程序实现 **IFreeBusySupport** 的 CLSID。 
    
2. 请Outlook设置以下注册表项来了解忙/闲提供程序是否存在 (其中表示系统注册表中的Outlook) `<xx.x>` 版本： 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   例如，如果传输提供程序是 SMTP，若要向 Microsoft Outlook 2010，请对下表中的数据设置以下键： 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |名称 |类型 |值 |
   |:-----|:-----|:-----|
   |SMTP  |REG_SZ  |{CLSID，用于实现 IFreeBusySupport}  |
   
   在此方案中，Outlook COM 类并使用它检索任何 SMTP 邮件用户的忙/闲信息。
    
若要支持使用 SMTP 地址条目类型的通讯簿和传输提供程序，请相应地更改 *Name。* 
  
> [!NOTE]
> 在安装过程中，忙/闲提供程序应检查同一地址条目类型的注册表设置是否已经存在。 如果是，则忙/闲提供程序应覆盖该地址条目类型的当前提供程序，在卸载时还原到该提供程序。 但是，如果用户为同一地址输入类型安装了多个忙/闲提供程序，则用户应按安装 (（即始终卸载最新的提供程序）的相反顺序卸载这些提供程序) 。 否则，注册表可能指向已卸载的提供程序。 
  
## <a name="api-components"></a>API 组件

忙/闲 API 包括以下组件：
  
### <a name="definitions"></a>定义

- [常量 (忙/闲 API) ](constants-free-busy-api.md)
    
### <a name="data-types"></a>数据类型

- [FBBlock_1](fbblock_1.md)
- [FBStatus](fbstatus.md)
- [FBUser](fbuser.md)
    
### <a name="interfaces"></a>接口

- [IEnumFBBlock](ienumfbblock.md)
- [IFreeBusyData](ifreebusydata.md)
- [IFreeBusySupport](ifreebusysupport.md)
    

