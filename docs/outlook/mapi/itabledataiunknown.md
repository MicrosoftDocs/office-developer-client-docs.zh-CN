---
title: ITableData IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData
api_type:
- COM
ms.assetid: ac7ae09f-ce19-45cf-8963-fad5bba75452
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bec68568b30bdc3112493a656de591f222801e46
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586240"
---
# <a name="itabledata--iunknown"></a>ITableData : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供用于处理表的实用程序方法。 MAPI 提供了实现**ITableData**帮助执行表维护的服务提供商的对象或表数据对象。 若要获取表数据对象，请服务提供商，请调用[CreateTable](createtable.md)函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|由公开：  <br/> |表格数据对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
|接口标识符：  <br/> |IID_IMAPITableData  <br/> |
|指针类型：  <br/> |LPTABLEDATA  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[HrGetView](itabledata-hrgetview.md) <br/> |创建表视图中，返回到[IMAPITable](imapitableiunknown.md)实现的指针。  <br/> |
|[HrModifyRow](itabledata-hrmodifyrow.md) <br/> |插入一个新的表格行，原因可能替换现有行。  <br/> |
|[HrDeleteRow](itabledata-hrdeleterow.md) <br/> |删除表格行。  <br/> |
|[HrQueryRow](itabledata-hrqueryrow.md) <br/> |检索表格行。  <br/> |
|[HrEnumRow](itabledata-hrenumrow.md) <br/> |检索根据其位置表中的行。  <br/> |
|[HrNotify](itabledata-hrnotify.md) <br/> |发送通知的表格行。  <br/> |
|[HrInsertRow](itabledata-hrinsertrow.md) <br/> |插入表格行。  <br/> |
|[HrModifyRows](itabledata-hrmodifyrows.md) <br/> |插入多个表行，原因可能替换现有行。  <br/> |
|[HrDeleteRows](itabledata-hrdeleterows.md) <br/> |删除多个表行。  <br/> |
   
## <a name="remarks"></a>注解

**ITableData**的 MAPI 实现适用于按住的所有数据和任何关联的限制，在内存中，使其适合用于非常大的表的表。 不支持大型限制和复杂操作，例如分类。 
  
表格数据对象标识行使用索引列，保证具有每个行的唯一值的属性。 大多数服务提供商使用的索引列作为**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 具有多个值的属性不能用作索引列。
  
表格数据对象生成单个通知无论受更改或删除的行数。 如果操作中的目标行不存在，将添加行。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

