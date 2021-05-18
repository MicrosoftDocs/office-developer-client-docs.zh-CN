---
title: MAPI 状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 38310619-1b1d-4934-8533-d0612676c0b0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 816d1b7c9c0b8c5a80a2351580ce3224fccf0b14
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406743"
---
# <a name="mapi-status-objects"></a>MAPI 状态对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Status 对象报告有关 MAPI 资源的信息。 例如，服务提供商、MAPI 发送/接收过程或通讯簿。
  
有一个状态对象提供有关当前配置文件中每个服务提供程序的信息。 MAPI 负责为子系统、MAPI 发送/接收过程和通讯簿实现状态对象。 子系统状态对象提供全局信息。 集成通讯簿的状态对象提供当前运行的所有通讯簿提供程序的状态。
  
每个状态对象都包含在状态表中，此表由 MAPI 维护，为客户端提供会话的所有状态信息。 有关详细信息，请参阅状态 [表](status-tables.md)。 客户端可以通过表或服务提供商的登录对象访问特定状态对象。 例如，若要访问通讯簿提供程序的状态对象，客户端可以调用 **IABLogon：：OpenStatusEntry**。 有关详细信息，请参阅 [IABLogon：：OpenStatusEntry](iablogon-openstatusentry.md)。
  
客户端可以使用 status 对象：
  
- 了解会话的状态。
    
- 监视服务提供商。
    
- 控制邮件传输。
    
- 查看或更改资源的配置和状态。
    
每个状态对象都实现 **IMAPIStatus** 接口。 有关详细信息，请参阅 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md)。 但是，不是每个状态对象都完全支持每个 **IMAPIStatus** 方法。 由于状态对象支持的方法存在差异，因此客户端需要先了解特定状态对象，然后才能使用它。 需要 Status 对象才能在下列三个属性中发布有关其功能的信息： 
  
 **PR_RESOURCE_METHODS (** [PidTagResourceMethods)](pidtagresourcemethods-canonical-property.md) 
  
 **PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md))  
  
 **PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md) 
  
有关实现状态对象的信息，请参阅 [状态对象实现](status-object-implementation.md)。 有关使用状态对象的信息，请参阅 [状态表和状态对象](status-table-and-status-objects.md)。
  

