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
ms.openlocfilehash: 91b1fa06fd47321e9c19d9751caac793e27e8f16
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778640"
---
# <a name="retrieving-data-from-table-rows"></a>从表行检索数据

  
  
**适用于**： Outlook 
  
从表中检索行包括：
  
- 获取所有列的属性值。
    
- 修改当前的位置。
    
大多数表中所需的列之一是条目标识符 — **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性 — 可用于打开代表行的对象。 此条目标识符通常为短期条目标识符，一个将不会过表的生存期。 但是，它可以是长期标识符，如果服务提供商实现表仅支持一种类型的项标识符。
  
客户端和服务提供商可以进行以下呼叫检索行之一：
  
|||
|:-----|:-----|
|[IMAPITable::QueryRows](imapitable-queryrows.md) <br/> |检索指定的开头中向前或向后方向的当前行的行数。  <br/> |
|[HrQueryAllRows](hrqueryallrows.md) <br/> |检索所有表中的行。  <br/> |
|[ITableData::HrQueryRow](itabledata-hrqueryrow.md) <br/> |检索其索引列的值根据表中的行。 **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 通常是表的索引列。  <br/> |
   
可选属性，包含作为一个表中的列时，某些行时其他人也可能不，可能有列的有效值。 一个有效的值是否存在列取决于是否提供行的信息的对象设置属性。 根据对象的实现，不存在属性可以表示为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 表或任意值中。 必须注意区分属性不存在且具有无意义的值和属性存在且具有有效的值的表的用户。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

