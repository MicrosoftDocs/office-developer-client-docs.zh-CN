---
title: 使用 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5f0e5c97-5089-47cb-b604-2292b2ff945c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4612b6f345d59d988013671758c6d0579aaa127d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569531"
---
# <a name="using-the-mapi-utilities"></a>使用 MAPI 实用工具

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 实用程序组成的表数据属性的数据对象和各种功能，以支持 miscellaneous 功能。 很可能为客户端需要仅这些实用程序并不需要登录到 MAPI 子系统建立与服务提供商的连接。 如果您的客户端符合此类别中，调用 API 函数[ScInitMapiUtil](scinitmapiutil.md)而不是[MAPIInitialize](mapiinitialize.md)函数在初始化时。 
  
 **ScInitMapiUtil**使客户端使用需要 MAPI 分配器，但的不询问的分配器明确的实用工具函数。 关闭时间后，调用[DeinitMapiUtil](deinitmapiutil.md)以释放资源，而不是[MAPIUninitialize](mapiuninitialize.md)。 从不呼叫**MAPIInitialize**的客户端不应调用**MAPIUninitialize**。
  
如果以前呼叫过**ScInitMapiUtil** ，而不是**MAPIInitialize**并通过**ITableData**方法，而不通过**IMAPITable**方法使用表，请注意，表通知不起作用。 通知要求使用 MAPI 库和[IMAPITable: IUnknown](imapitableiunknown.md)。
  

