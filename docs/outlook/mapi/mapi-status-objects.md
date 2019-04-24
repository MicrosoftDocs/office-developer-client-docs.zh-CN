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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309532"
---
# <a name="mapi-status-objects"></a>MAPI 状态对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
状态对象报告有关 MAPI 资源的信息。 例如, 服务提供商、MAPI 发送/接收进程或通讯簿。
  
有一个 status 对象, 提供有关当前配置文件中每个服务提供程序的信息。 mapi 负责实现子系统、MAPI 发送/接收进程和通讯簿的状态对象。 子系统状态对象提供全局信息。 集成通讯簿的 status 对象提供当前正在运行的所有通讯簿提供程序的状态。
  
每个 status 对象都包含在状态表中, 由 MAPI 维护的表, 为客户端提供会话的所有状态信息。 有关详细信息, 请参阅[状态表](status-tables.md)。 客户端可以通过表或服务提供商 (通过其登录对象) 访问特定的状态对象。 例如, 若要访问通讯簿提供程序的 status 对象, 客户端可以调用**IABLogon:: OpenStatusEntry**。 有关详细信息, 请参阅[IABLogon:: OpenStatusEntry](iablogon-openstatusentry.md)。
  
客户端可以使用 status 对象执行以下操作:
  
- 了解会话的状态。
    
- 监视服务提供商。
    
- 控制邮件传输。
    
- 查看或更改资源的配置和状态。
    
每个 status 对象都实现**IMAPIStatus**接口。 有关详细信息, 请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。 但是, 并不是每个 status 对象完全支持每个**IMAPIStatus**方法。 由于 status 对象支持的方法有变体, 因此客户端需要先了解特定状态对象, 然后才能使用该对象。 必须有 Status 对象才能发布以下三个属性中有关其功能的信息: 
  
 **PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 
  
 **PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 
  
 **PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 
  
有关实现 status 对象的详细信息, 请参阅[status object 实现](status-object-implementation.md)。 有关使用 status 对象的详细信息, 请参阅[status Table 和 status 对象](status-table-and-status-objects.md)。
  

