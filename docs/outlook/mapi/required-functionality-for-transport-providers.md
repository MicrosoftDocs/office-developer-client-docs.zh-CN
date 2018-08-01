---
title: 传输提供程序的必需功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0d9a3e0-a500-4d72-8859-ecfd1604fc5b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eb5d70c31f28df16593fb020f13124ea217476ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778642"
---
# <a name="required-functionality-for-transport-providers"></a>传输提供程序的必需功能

  
  
**适用于**： Outlook 
  
每个 MAPI 传输提供程序必须：
  
- 遵循使用 MAPI 和其他服务提供商的一般指南。 有关详细信息，请参阅[MAPI 应用程序开发](mapi-application-development.md)和[MAPI 服务提供商](mapi-service-providers.md)。
    
- 具有其传输提供程序为 MAPI DLL 公开其[XPProviderInit](xpproviderinit.md)初始化函数。 
    
- 为 MAPI 公开其实现[IXPProvider: IUnknown](ixpprovideriunknown.md)和[IXPLogon: IUnknown](ixplogoniunknown.md)接口。 
    
- MAPI 和客户端应用程序公开其实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 有关实现**IMAPIStatus**的详细信息，请参阅[状态对象实现](status-object-implementation.md)。 
    
- 实现属性表对话框进行配置。 有关实现属性表的详细信息，请参阅[属性表实现](property-sheet-implementation.md)。
    

