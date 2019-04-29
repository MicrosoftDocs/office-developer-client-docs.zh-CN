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
  
每个 MAPI 传输提供程序都必须:
  
- 遵循有关使用 MAPI 和其他服务提供商的一般准则。 有关详细信息, 请参阅[MAPI 应用程序开发](mapi-application-development.md)和[MAPI 服务提供程序](mapi-service-providers.md)。
    
- 让其传输提供程序 DLL 向 MAPI 公开其[XPProviderInit](xpproviderinit.md)初始化功能。 
    
- 向 MAPI 公开其[IXPProvider: iunknown](ixpprovideriunknown.md)和[IXPLogon: iunknown](ixplogoniunknown.md)接口的实现。 
    
- 向 MAPI 和客户端应用程序公开[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口的实现。 有关实现**IMAPIStatus**的详细信息, 请参阅[Status Object 实现](status-object-implementation.md)。 
    
- 为配置实现 "属性表" 对话框。 有关实现属性表的详细信息, 请参阅[property Sheet 实现](property-sheet-implementation.md)。
    

