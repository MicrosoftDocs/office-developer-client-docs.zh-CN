---
title: 关于忙/闲 API
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 17c5e44e-ae56-8de7-3579-90171d996411
description: 忙/闲 API 允许邮件提供商提供指定的用户帐户指定的时间范围内的忙/闲状态信息。
ms.openlocfilehash: 8b1559173297fbde9930b6f8f7fbc74f176273da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774169"
---
# <a name="about-the-freebusy-api"></a>关于忙/闲 API

忙/闲 API 允许邮件提供商提供指定的用户帐户指定的时间范围内的忙/闲状态信息。 某一用户的日历时间的忙/闲状态是以下项之一:-外出、 忙碌、 暂定、 或免费。
  
## <a name="create-a-freebusy-provider"></a>创建一个忙/闲提供程序

若要提供向邮件用户的忙/闲信息，邮件提供商创建忙/闲提供程序，并将其注册与 Outlook。 忙/闲提供程序必须实现以下接口。 请注意，这些接口中的成员数不受支持，并且必须返回指定的返回值。 具体而言，忙/闲 API 不支持写访问权忙/闲信息和委派对帐户的访问。
  
- [IFreeBusySupport](ifreebusysupport.md) — 此接口支持接口访问指定的用户的忙/闲数据的规范。 它使用[FBUser](fbuser.md)标识用户。 
    
- [IFreeBusyData](ifreebusydata.md) — 此接口获取和设置给定用户的时间范围并返回枚举忙/闲此时间范围内的数据块界面。 它使用相对时间来获取和设置此时间范围。 有关详细信息，请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。
    
- [IEnumFBBlock](ienumfbblock.md) — 此接口支持访问和枚举忙/闲时间范围内的用户数据块。 
    
   > [!NOTE]
   > 枚举包含指示在用户的日历上，在 （指定[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)） 的时间范围内的时间段内的忙/闲状态的忙/闲块。 在日历上，如约会和会议请求项目表单块枚举中。 紧邻日历上的另一且具有相同的忙/闲状态的项目组合到一个单个块的窗体。 一段空闲时期的日历时间也形成块。 因此，无枚举中的两个连续块会具有相同的忙/闲状态。 这些块不时间重叠。 当日历上存在重叠的项目时，Outlook 将合并这些项目以形成枚举基于以下优先顺序中的非重叠忙/闲基块:-外出、 忙碌、 暂定。 
  
若要注册与 Outlook 的忙/闲提供程序，邮件提供商应执行以下操作：
  
1. 将忙/闲提供程序注册 COM，提供允许访问提供程序的实现**IFreeBusySupport**CLSID。 
    
2. 让知道的忙/闲提供程序存在通过设置以下项的 Outlook (其中`<xx.x>`表示的 Outlook 版本) 系统注册表中： 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\<xx.x>\Outlook\SchedulingInformation\FreeBusySupport`
    
   例如，如果 SMTP 传输提供程序，可提供程序注册到 Microsoft Outlook 2010 中，设置以下项下表中的数据： 
    
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook\SchedulingInformation\FreeBusySupport`
    
   |名称 |类型 |值 |
   |:-----|:-----|:-----|
   |SMTP  |REG_SZ  |{CLSID 各自实现 IFreeBusySupport}  |
   
   在此方案中，Outlook 共同创建 COM 类，并使用它来检索任何 SMTP 邮件用户的忙/闲信息。
    
若要支持使用之外的 SMTP 地址条目类型的通讯簿和传输提供程序，相应地更改*名称*。 
  
> [!NOTE]
> 安装过程中，应检查忙/闲提供程序，是否的注册表设置相同的地址条目类型已存在。 如果是这样的忙/闲提供程序应覆盖的当前提供程序的地址条目类型，并还原到该提供程序，它卸载时。 但是，如果用户具有安装相同的地址条目类型的多个忙/闲提供程序，用户应卸载这些提供程序安装的相反的顺序 （即，始终卸载的最新的提供程序）。 否则，注册表可能会导致的提供程序已卸载。 
  
## <a name="api-components"></a>API 组件

忙/闲 API 包括以下组件：
  
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
    

