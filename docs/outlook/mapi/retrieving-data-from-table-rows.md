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
  
从表中检索行涉及：
  
- 获取所有列的属性值。
    
- 修改当前位置。
    
大多数表中所需的列之一是条目标识符 **（PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性）可用于打开表示该行的对象。 此条目标识符通常是一个短期条目标识符，一个不会在表的生存期之后仍然保留的标识符。 但是，如果实现表的服务提供商仅支持一种类型的条目标识符，则它可以是长期标识符。
  
客户端和服务提供商可以进行以下调用之一来检索行：
  
|||
|:-----|:-----|
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |以向前或向后方向检索以当前行开始指定的行数。  <br/> |
|[HrQueryAllRows](hrqueryallrows.md) <br/> |检索表中的所有行。  <br/> |
|[ITableData::HrQueryRow](itabledata-hrqueryrow.md) <br/> |根据索引列的值检索表格中的行。 **PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 通常是表的索引列。  <br/> |
   
当可选属性作为表中的列之一包含时，一些行可能具有该列的有效值，而其他行可能没有。 列是否存在有效值取决于提供行信息的对象是否设置属性。 根据对象的实现，表中不存在的属性可以表示为 PR_NULL ([PidTagNull](pidtagnull-canonical-property.md) ) 或任意值。 表的用户必须小心区分不存在、具有无意义的值和具有有效值的属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

