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
ms.openlocfilehash: 86aa8451b5b127764134f1a3a905366fd014d0c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430628"
---
# <a name="mapi-implemented-objects"></a>MAPI 实现的对象
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 实现了多个对象, 以供客户端应用程序和服务提供程序使用。 session 对象允许客户端使用会话服务访问表, 并与服务提供商进行通信。 通讯簿对象为客户端提供了对所有不同通讯簿提供程序的集成访问权限。 
  
MAPI 提供多个表和状态对象, 供客户端用来查看和监视会话和服务提供程序信息。 例如, MAPI 提供了一个配置文件表, 其中包含有关安装在计算机上的所有配置文件的信息, 以及有关当前配置文件中的所有邮件服务的信息的邮件服务表。 MAPI 提供了三个不同的状态对象: 一个代表整个子系统, 一个用于 MAPI 后台处理程序, 另一个用于集成的通讯簿。 
  
MAPI 实现了四个不同的对象, 用于管理邮件服务、服务提供程序和配置文件的配置。 客户端和服务提供程序都使用提供程序管理和配置文件部分对象;这些对象使他们能够配置服务提供程序和访问配置文件属性。 客户端仅使用邮件服务和配置文件管理对象、支持邮件服务和配置文件管理的对象。 
  
MAPI 为服务提供程序提供了两个对象: 一个支持对象和一个 TNEF 对象。 所有服务提供程序都使用一个或多个支持对象;有四种不同的支持对象实现。 MAPI 提供实现以支持配置的实现, 以及支持通讯簿、邮件存储和传输提供程序的特定实现。 TNEF 对象由支持传输中性封装格式 (TNEF) 的传输提供程序使用。
  
两个实用工具对象、表数据和属性数据通常由服务提供程序使用。 table data 对象有助于实现 table 对象;属性数据对象可帮助您在[IMAPIProp: IUnknown](imapipropiunknown.md)、base 属性接口的实现中设置和查看属性访问和帮助。 
  
下表汇总了 MAPI 实现的每个对象的用途。
  
|**MAPI 对象**|**说明**|
|:-----|:-----|
|通讯簿  <br/> |提供对属于活动配置文件中的所有通讯簿提供程序的收件人信息的集成视图的访问。  <br/> |
|邮件服务管理  <br/> |提供对用于配置的邮件服务信息的访问权限。  <br/> |
|配置文件管理  <br/> |提供对配置文件信息的访问。  <br/> |
|Profile 部分  <br/> |用于描述特定邮件服务或服务提供商的配置文件的一部分。  <br/> |
|属性数据  <br/> |维护对属性的访问并帮助实现**IMAPIProp**。  <br/> |
|提供程序管理  <br/> |提供对用于配置的服务提供程序信息的访问。  <br/> |
|Session  <br/> |表示与基础邮件系统的连接, 并为客户端提供对 MAPI 资源的访问权限。  <br/> |
|状态  <br/> |提供对 mapi 子系统、通讯簿或 MAPI 后台处理程序的状态的访问。  <br/> |
|支持  <br/> |帮助服务提供程序处理客户端请求。  <br/> |
|Table  <br/> |提供对行和列格式的对象数据的摘要视图, 与数据库表类似。  <br/> |
|表数据  <br/> |维护对基础表数据的访问和实现表对象。  <br/> |
|TNEF  <br/> |支持使用传输中性封装格式 (TNEF)。  <br/> |
   
下图显示了 MAPI 实现的对象、它们继承到的接口以及使用它们的组件之间的关系。 
  
**MAPI 实现的对象**
  
![MAPI 实现的对象](media/amapi_68.gif "MAPI 实现的对象")
  
## <a name="see-also"></a>另请参阅

- [IMAPIProp : IUnknown](imapipropiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

