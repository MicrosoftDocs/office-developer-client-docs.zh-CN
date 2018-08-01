---
title: 保存 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ed0c14f9-3dcf-49ad-928e-ba872d4d6b5a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6135dfae915a1e70743f9224352390c4b56ea02e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778664"
---
# <a name="saving-mapi-properties"></a>保存 MAPI 属性

  
  
**适用于**： Outlook 
  
很多对象支持事务处理，对属性的更改不会成为永久性直到提交稍后由此模型。 由[IMAPIProp::SetProps](imapiprop-setprops.md)和[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)方法处理对属性的更改，而是由[IMAPIProp::SaveChanges](imapiprop-savechanges.md)处理提交步骤。 此文件不成功调用**SaveChanges**可访问对象的属性的最新版本之后。 
  
当**SaveChanges**将返回错误值 MAPI_E_OBJECT_CHANGED 时，这是一条警告，另一个客户端同时将对对象提交的更改。 有可能，具体取决于提供程序成功实现多个客户端到该对象，通过调用设置了 MAPI_MODIFY 标志其**OpenEntry**方法授予他们读/写访问权限打开对象。 返回从例如**OpenEntry**呼叫是存储数据的快照的对象。 每个后续尝试更改此数据可以覆盖上一次尝试。 
  
在从**SaveChanges**收到 MAPI_E_OBJECT_CHANGED，客户端还提供了选项： 
  
- 创建要保存所做的更改的对象的副本。
    
- 发起**SaveChanges**，指定 FORCE_SAVE 到另一个呼叫。 
    
使用 FORCE_SAVE 标志调用**SaveChanges**覆盖以前保存，并使客户端的更改永久。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

