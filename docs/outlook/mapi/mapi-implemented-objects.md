---
title: MAPI 实现的对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5d07c259-0ceb-4ea5-98b4-b01720edfe2a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d212a86aae0503a5e02a5a7ecddb83db10a4d664
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572373"
---
# <a name="mapi-implemented-objects"></a>MAPI 实现的对象
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 实现供客户端应用程序和服务提供商使用的多个对象。 会话对象允许客户端用于会话服务，以访问表，以及与服务提供商进行通信。 通讯簿对象提供对不同的地址簿提供程序的所有客户端集成的访问。 
  
MAPI 提供客户端，用于查看和监视会话和服务提供程序信息的多个表和状态的对象。 例如，MAPI 提供了有关所有计算机安装的配置文件信息与配置文件表和消息服务表与有关当前配置文件中的消息服务的所有信息。 MAPI 提供了三个不同的状态对象： 一个值，该值代表总体子系统，一个用于 MAPI 后台处理程序，，一个用于集成的通讯簿。 
  
MAPI 实现用于管理的消息服务、 服务提供商和配置文件配置的四个不同对象。 客户端和服务提供商使用提供程序管理和 profile section 对象;这些对象使用户能够配置服务提供商和访问配置文件属性。 客户端使用仅消息服务和配置文件管理对象，支持管理消息服务和配置文件的对象。 
  
MAPI 服务提供程序提供了两个对象： 支持对象和 TNEF 对象。 所有服务提供商都使用一个或多个支持对象;有四个不同的支持对象实现。 MAPI 提供实现以支持配置以及特定的实现，以支持通讯簿、 消息存储和传输提供程序。 传输提供程序支持传输中性封装格式 (TNEF) 使用 TNEF 对象。
  
两个实用程序对象、 表格数据和属性数据通常由服务提供商使用。 表格数据对象中的 table 对象; 实现帮助属性集和视图属性访问和帮助实现中的数据对象帮助[IMAPIProp: IUnknown](imapipropiunknown.md)，基属性接口。 
  
下表总结了 MAPI 实现的每个对象的目的。
  
|**MAPI 对象**|**说明**|
|:-----|:-----|
|通讯簿  <br/> |提供对综合视图所属的通讯簿提供程序的活动配置文件中所有的收件人信息的访问。  <br/> |
|消息 service 管理  <br/> |提供对邮件服务信息配置的访问。  <br/> |
|配置文件管理  <br/> |提供用于配置对配置文件信息的访问。  <br/> |
|配置文件节  <br/> |用来描述一个特定消息服务或服务提供程序配置文件的一部分。  <br/> |
|属性数据  <br/> |维护对属性的访问，并帮助实现**IMAPIProp**。  <br/> |
|提供程序管理  <br/> |提供对配置访问服务提供商信息。  <br/> |
|会话  <br/> |代表与基础邮件系统的连接和客户端提供对 MAPI 资源的访问。  <br/> |
|Status  <br/> |提供对 MAPI 子系统、 通讯簿中或 MAPI 后台处理程序的状态的访问。  <br/> |
|支持  <br/> |可帮助处理客户端请求的服务提供商。  <br/> |
|Table  <br/> |提供对行和列的格式，类似于数据库表中的对象数据的摘要视图访问。  <br/> |
|表数据  <br/> |维护到基础表数据的访问，并实现 table 对象。  <br/> |
|TNEF  <br/> |支持使用的传输中性封装格式 (TNEF)。  <br/> |
   
下图显示 MAPI 实现的对象、 它们继承的接口和使用这些组件之间的关系。 
  
**MAPI 实现的对象**
  
![MAPI 实现的对象](media/amapi_68.gif "MAPI 实现的对象")
  
## <a name="see-also"></a>另请参阅

- [IMAPIProp : IUnknown](imapipropiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

