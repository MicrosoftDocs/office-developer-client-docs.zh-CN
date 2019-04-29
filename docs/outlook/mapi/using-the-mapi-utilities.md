---
title: 使用 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5f0e5c97-5089-47cb-b604-2292b2ff945c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8ec18ee7b80d8603266cf827f9484ee85bdb03c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409984"
---
# <a name="using-the-mapi-utilities"></a>使用 MAPI 实用工具

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 实用程序由表数据和属性数据对象以及用于支持杂项功能的各种函数组成。 客户端可以只需要这些实用程序, 而无需登录到 MAPI 子系统即可与服务提供商建立连接。 如果您的客户端符合此类别, 请在初始化时调用 API 函数[ScInitMapiUtil](scinitmapiutil.md) , 而不是[MAPIInitialize](mapiinitialize.md)函数。 
  
 **ScInitMapiUtil**使客户端能够使用需要 MAPI allocators 的实用工具函数, 但不会显式请求 allocators。 当需要关机时, 请调用[DeinitMapiUtil](deinitmapiutil.md)以释放资源, 而不是[MAPIUninitialize](mapiuninitialize.md)。 从不调用**MAPIInitialize**的客户端不应调用**MAPIUninitialize**。
  
如果您已调用**ScInitMapiUtil**而不是**MAPIInitialize** , 并且通过**ITableData**方法而不是使用**IMAPITable**方法使用表, 请注意, 表通知将不起作用。 通知需要使用 MAPI 库和[IMAPITable: IUnknown](imapitableiunknown.md)。
  

