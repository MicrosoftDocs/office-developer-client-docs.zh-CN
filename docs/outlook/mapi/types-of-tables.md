---
title: 表的类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1fc4f20-511f-4721-8f09-ec2a5fd0ccb0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 732b3d724c855d978250afff3d05c7f19909a5b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356572"
---
# <a name="types-of-tables"></a>表的类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有许多不同类型的表, 每种类型都由它所提供的信息进行区分。 通过表, 客户端应用程序和服务提供程序可以轻松访问和操作许多类型的对象的重要属性。 
  
某些表格 (如内容表格) 提供了访问属性的另一种方法。 例如, 客户端可以通过调用其[IMAPIProp:: GetProps](imapiprop-getprops.md)方法或通过邮件的内容表, 直接从邮件中检索邮件的主题 (其**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性)。 其他表提供了访问对象属性的唯一方法。 例如, 客户端无法通过调用 IMAPIProp 访问附件的**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性 **:: GetProps**;它必须始终检索其所附加到的邮件的附件表。 **PR_ATTACH_METHOD**是所有附件表中的必需列。 
  
表视图可以是静态的, 也可以是动态的。 使用静态表视图时, 对基础数据所做的更改不会导致视图更新。 视图实例化后, 它不会发生变化。 可以通过表通知通知静态表的用户更改数据。 在对数据进行更改时更新动态表格视图。 有两种类型的动态表格: 一种是更新每行的列, 但行保持静态, 同时更新列和行。 后一种类型的表总是完全反映基础数据。
  
表具有默认列集, 在从尚未受到[IMAPITable:: SetColumns](imapitable-setcolumns.md)调用的表中检索行时, 客户端或服务提供商可以预期看到的最小列集。 客户端和服务提供程序可以通过调用**SetColumns**方法, 在此默认集合中添加或删除列。 可以在客户端请求的后面以静态或动态方式进行更改。 并非所有表都支持动态列集修改。 
  
MAPI 表及其实施者和用户为:
  
|**Table**|**方**|
|:-----|:-----|
|附件  <br/> |由邮件存储提供程序实现。 由客户端和传输提供程序使用。  <br/> |
|目录  <br/> |由邮件存储和通讯簿提供程序实现。 由客户端使用。  <br/> |
|显示  <br/> |由 MAPI 和服务提供商实现。 由 MAPI 和服务提供商使用。  <br/> |
|Hierarchy  <br/> |由邮件存储和通讯簿提供程序实现。 由客户端使用。  <br/> |
|邮件服务  <br/> |由 MAPI 实现。 由客户端使用。  <br/> |
|邮件存储  <br/> |由 MAPI 实现。 由客户端使用。  <br/> |
|一次性  <br/> |由通讯簿提供程序实现。 由 MAPI 使用。  <br/> |
|传出队列  <br/> |由邮件存储提供程序实现。 由 MAPI 后台处理程序使用。  <br/> |
|配置文件  <br/> |由 MAPI 实现。 由客户端使用。  <br/> |
|提供程序  <br/> |由 MAPI 实现。 由客户端使用。  <br/> |
|接收文件夹  <br/> |由邮件存储提供程序实现。 由客户端使用。  <br/> |
|收件人  <br/> |由邮件存储提供程序实现。 由客户端和传输提供程序使用。  <br/> |
|状态  <br/> |由 MAPI 和服务提供商实现。 由客户端使用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

