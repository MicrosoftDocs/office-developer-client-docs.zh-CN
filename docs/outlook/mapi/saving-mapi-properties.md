---
title: 保存 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ed0c14f9-3dcf-49ad-928e-ba872d4d6b5a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5d4653492028151d7e19a5d5490c8c8949002a4f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425888"
---
# <a name="saving-mapi-properties"></a>保存 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多对象支持处理的事务模型, 对属性所做的更改不会永久成为永久更改, 除非在以后提交它们。 而对属性的更改由[IMAPIProp:: SetProps](imapiprop-setprops.md)和[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)方法处理, 则 commit 步骤将由[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)处理。 在成功调用某个对象的属性的**** 最新版本之前, 此方法不会一直发生。 
  
当**SaveChanges**返回错误值 MAPI_E_OBJECT_CHANGED 时, 这是一个警告, 指出另一个客户端同时提交对该对象的更改。 根据实现对象的提供程序的不同, 多个客户端可以通过调用其**OpenEntry**方法并设置 MAPI_MODIFY 标志来成功打开对象, 从而为它们提供读/写访问权限。 从这样的**OpenEntry**调用返回的对象是存储数据的快照。 随后每次尝试更改此数据时, 都可能会覆盖之前的尝试。 
  
在从**SaveChanges**接收 MAPI_E_OBJECT_CHANGED 时, 客户端可以选择执行以下操作: 
  
- 创建对象的副本以保存所做的更改。
    
- 对**SaveChanges**调用另一个调用, 指定 FORCE_SAVE。 
    
使用 FORCE_SAVE 标志调用**SaveChanges**将覆盖上一次保存, 并使客户端的更改永久化。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

