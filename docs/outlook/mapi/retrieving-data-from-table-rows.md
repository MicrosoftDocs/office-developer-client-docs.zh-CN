---
title: 从表行检索数据
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19a42794-a3a2-4336-af2a-473f24431252
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2f389d26ec80b9af3ed28c5eb85b589c9cbb26c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405252"
---
# <a name="retrieving-data-from-table-rows"></a>从表行检索数据

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索表中的行涉及:
  
- 获取所有列的属性值。
    
- 修改当前位置。
    
大多数表中的必需列之一是条目标识符 ( **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性), 可用于打开代表该行的对象。 此条目标识符通常是短期条目标识符, 不会保留在表的生存期之后。 但是, 如果实现表的服务提供程序仅支持一种类型的条目标识符, 则它可以是长期标识符。
  
客户端和服务提供商可以执行以下调用之一来检索行:
  
|||
|:-----|:-----|
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |检索以正向或向后方向从当前行开始的指定数量的行。  <br/> |
|[HrQueryAllRows](hrqueryallrows.md) <br/> |检索表中的所有行。  <br/> |
|[ITableData::HrQueryRow](itabledata-hrqueryrow.md) <br/> |根据索引列的值检索表中的行。 **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 通常是表的索引列。  <br/> |
   
如果可选属性作为表中的列之一包含, 则某些行可能具有列值的有效值, 而其他可能不是。 是否存在列值的有效值取决于提供行信息的对象是否设置属性。 根据对象的实现方式, 不存在的属性可以在表中表示为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 或任意值。 表的用户必须小心区分不存在的属性以及确实存在无意义的值和属性, 并使其具有有效的值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

