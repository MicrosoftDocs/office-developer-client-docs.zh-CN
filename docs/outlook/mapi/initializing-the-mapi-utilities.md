---
title: 初始化 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02b14285-bbef-44f2-b2a4-45d96395998a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5c5a9355e9edec28e08986ccd055fc43eec7b974
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420946"
---
# <a name="initializing-the-mapi-utilities"></a>初始化 MAPI 实用工具

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果您需要使用的 MAPI 的唯一部分是实用程序, 则是在 MAPI 的 MAPIUTIL 中声明的接口和函数。H 头文件 (如**IPropData**和**ITableData** ) 不需要调用**MAPIInitialize**进行初始化。 有关详细信息, 请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md)、 [ITableData: IUnknown](itabledataiunknown.md)和[MAPIInitialize](mapiinitialize.md)。 而是调用**ScInitMapiUtil**函数。 有关详细信息, 请参阅[ScInitMapiUtil](scinitmapiutil.md)。 **ScInitMapiUtil**使客户端应用程序能够使用需要 MAPI allocators 的实用工具函数和方法, 但这不会对其进行显式请求。 
  
在关机时, 调用**DeinitMapiUtil**以释放连接到这些实用程序的资源。 请勿调用**MAPIUninitialize**。 有关详细信息, 请参阅[DeinitMapiUtil](deinitmapiutil.md)和[MAPIUninitialize](mapiuninitialize.md)。
  
请注意, **ITableData**接口不支持已调用**ScInitMapiUtil**而不是**MAPIInitialize**的客户端的表通知。 
  

