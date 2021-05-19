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
  
许多对象都支持处理事务模型，在稍后提交属性之前，对属性的更改不会永久进行。 而对属性的更改由 [IMAPIProp：：SetProps](imapiprop-setprops.md) 和 [IMAPIProp：:D eleteProps](imapiprop-deleteprops.md) 方法处理，而提交步骤由 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)处理。 直到成功调用 **SaveChanges** 之后，才能访问对象的属性的最新版本。 
  
当 **SaveChanges** 返回错误值MAPI_E_OBJECT_CHANGED，这是一条警告，提示另一个客户端同时向对象提交更改。 多个客户端通过调用其 **OpenEntry** 方法并设置 MAPI_MODIFY 标志，从而成功地打开对象，具体取决于实现对象的提供程序。 从此类 **OpenEntry** 调用返回的对象是存储数据的快照。 每次更改此数据的后续尝试都可能会覆盖上一次尝试。 
  
从 **SaveChanges** MAPI_E_OBJECT_CHANGED时，客户端可以选择： 
  
- 创建对象的副本以保存更改。
    
- 对 **SaveChanges 进行** 另一个调用，指定FORCE_SAVE。 
    
调用具有 FORCE_SAVE 标志的 **SaveChanges** 会覆盖上一次保存，并永久更改客户端。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

