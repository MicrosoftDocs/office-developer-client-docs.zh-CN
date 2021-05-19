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
  
MAPI 实用程序由表数据和属性数据对象以及各种函数（以支持杂项功能）所决定。 客户端可能只需要这些实用程序，并且不必登录到 MAPI 子系统来与服务提供商建立连接。 如果你的客户端适合此类别，在初始化时调用 API 函数 [ScInitMapiUtil](scinitmapiutil.md) 而不是 [MAPIInitialize](mapiinitialize.md) 函数。 
  
 **ScInitMapiUtil** 使客户端可以使用需要 MAPI 分配器，但不显式请求分配器的实用程序函数。 当需要关闭时，调用 [DeinitMapiUtil](deinitmapiutil.md) 以释放资源，而不是 [MAPIUninitialize](mapiuninitialize.md)。 从不调用 **MAPIInitialize** 的客户端不应调用 **MAPIUninitialize**。
  
如果已调用 **ScInitMapiUtil** 而不是 **MAPIInitialize，** 并且正通过 **ITableData** 方法而不是 **IMAPITable** 方法使用表，请注意表通知将不起作用。 通知需要使用 MAPI 库和 [IMAPITable ： IUnknown](imapitableiunknown.md)。
  

