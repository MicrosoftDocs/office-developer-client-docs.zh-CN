---
title: 传输提供程序所需的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0d9a3e0-a500-4d72-8859-ecfd1604fc5b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f9768d47cf740bdf50b439ee3af4b0d2a191602
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404440"
---
# <a name="required-functionality-for-transport-providers"></a>传输提供程序所需的功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个 MAPI 传输提供程序都必须：
  
- 遵循使用 MAPI 和其他服务提供商的一般准则。 有关详细信息，请参阅 [MAPI 应用程序开发和](mapi-application-development.md) [MAPI 服务提供程序](mapi-service-providers.md)。
    
- 将其传输提供程序 DLL 公开到 MAPI 其 [XPProviderInit](xpproviderinit.md) 初始化函数。 
    
- 向 MAPI 公开 [IXPProvider ： IUnknown](ixpprovideriunknown.md) 和 [IXPLogon ： IUnknown](ixplogoniunknown.md) 接口的实现。 
    
- 向 MAPI 和客户端应用程序公开其 [IMAPIStatus ： IMAPIProp 接口](imapistatusimapiprop.md) 的实现。 有关实现 **IMAPIStatus** 的信息，请参阅 [状态对象实现](status-object-implementation.md)。 
    
- 实现属性表配置对话框。 有关实现属性表的信息，请参阅 [属性表实现](property-sheet-implementation.md)。
    

