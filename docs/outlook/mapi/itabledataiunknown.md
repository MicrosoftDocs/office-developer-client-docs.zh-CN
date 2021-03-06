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
ms.openlocfilehash: 3992bea899239ee5975505dec366490d6bbe1698
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430593"
---
# <a name="itabledata--iunknown"></a>ITableData : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供用于处理表的实用程序方法。 MAPI 提供实现 **ITableData** 的表数据对象，以帮助服务提供商执行表维护。 若要获取表数据对象，服务提供商调用 [CreateTable](createtable.md) 函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|公开者：  <br/> |表数据对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
|接口标识符：  <br/> |IID_IMAPITableData  <br/> |
|指针类型：  <br/> |LPTABLEDATA  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[HrGetView](itabledata-hrgetview.md) <br/> |创建表视图，返回指向 [IMAPITable](imapitableiunknown.md) 实现指针。  <br/> |
|[HrModifyRow](itabledata-hrmodifyrow.md) <br/> |插入新的表格行，可能会替换现有的行。  <br/> |
|[HrDeleteRow](itabledata-hrdeleterow.md) <br/> |删除表格行。  <br/> |
|[HrQueryRow](itabledata-hrqueryrow.md) <br/> |检索表行。  <br/> |
|[HrEnumRow](itabledata-hrenumrow.md) <br/> |根据行在表中的位置检索行。  <br/> |
|[HrNotify](itabledata-hrnotify.md) <br/> |发送表行的通知。  <br/> |
|[HrInsertRow](itabledata-hrinsertrow.md) <br/> |插入表格行。  <br/> |
|[HrModifyRows](itabledata-hrmodifyrows.md) <br/> |插入多个表格行，可能会替换现有行。  <br/> |
|[HrDeleteRows](itabledata-hrdeleterows.md) <br/> |删除多个表格行。  <br/> |
   
## <a name="remarks"></a>备注

**ITableData** 的 MAPI 实现通过将所有数据和任何关联限制都存储到内存中来使用表，从而不适合用于非常大的表。 不支持大型限制和复杂操作，如分类。 
  
表数据对象通过使用索引列来标识行，索引列是保证每行具有唯一值的属性。 大多数服务提供商使用[PidTagInstanceKey PR_INSTANCE_KEY (PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性作为索引列。  具有多个值的属性不能用作索引列。
  
无论受更改或删除影响的行数如何，表数据对象都会生成单个通知。 如果操作中的目标行不存在，则添加一行。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

