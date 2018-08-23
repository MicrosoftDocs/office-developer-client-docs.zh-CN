---
title: MAPI 状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 38310619-1b1d-4934-8533-d0612676c0b0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 69a4d25fc6a7abec68c94cc947e5944322d230a6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594948"
---
# <a name="mapi-status-objects"></a>MAPI 状态对象

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
状态对象报告 MAPI 资源的信息。 例如，服务提供程序、 MAPI 发送/接收进程或通讯簿。
  
没有状态对象提供有关当前配置文件中每个单独的服务提供商的信息。 MAPI 负责实现子系统、 MAPI 发送/接收过程和通讯簿状态对象。 子系统状态对象提供全球信息。 集成的通讯簿的状态对象提供的正在运行的所有通讯簿提供程序的状态。
  
在状态表中，客户端提供的所有会话状态信息的 MAPI 维护的表包含每个状态对象。 有关详细信息，请参阅[状态表](status-tables.md)。 客户端可以访问的特定状态对象，通过表或，针对服务提供程序，通过其登录对象。 例如，若要访问通讯簿提供程序的状态对象，客户端可以调用**IABLogon::OpenStatusEntry**。 有关详细信息，请参阅[IABLogon::OpenStatusEntry](iablogon-openstatusentry.md)。
  
客户端可以使用状态对象：
  
- 了解有关会话的状态信息。
    
- 监视服务提供商。
    
- 控制消息传输。
    
- 查看或更改资源的配置和状态。
    
每个状态对象实现**IMAPIStatus**接口。 有关详细信息，请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。 但是，不是每个状态对象完全支持每个**IMAPIStatus**方法。 因为没有状态对象支持的方法中的变体，客户端需要了解的特定状态对象，然后才能使用它。 状态对象所需的以下三个属性中发布有关其功能的信息： 
  
 **PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 
  
 **PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 
  
 **PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 
  
有关实现状态对象的详细信息，请参阅[状态对象实现](status-object-implementation.md)。 有关使用状态对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。
  

