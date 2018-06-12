---
title: TABLE_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.TABLE_NOTIFICATION
api_type:
- COM
ms.assetid: 48e478c4-6e9a-40ab-a7bb-e6219b743b08
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: fd77473ce728a51220a4c039f1d12d03d90e7f36
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778963"
---
# <a name="tablenotification"></a>TABLE_NOTIFICATION

**适用于**： Outlook 
  
介绍受某些类型的事件，如错误或更改表中的行。 这会导致表通知要生成。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _TABLE_NOTIFICATION
{
  ULONG ulTableEvent;
  HRESULT hResult;
  SPropValue propIndex;
  SPropValue propPrior;
  SRow row;
} TABLE_NOTIFICATION;

```

## <a name="members"></a>成员

**ulTableEvent**
  
> 用于表示表事件类型的标志位掩码。 可以设置以下标志：
    
TABLE_CHANGED 
  
> 指示在高级别已更改内容的表。 表的状态是前的事件。 这意味着所有**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性、 书签、 当前定位和用户界面选择都仍然有效。 通过重新读取表处理此事件。 要实现富表通知的服务提供商发送 TABLE_CHANGED 事件，而不是更详细的事件，以指示特定类型的更改。 
    
TABLE_ERROR 
  
> 出错，通常在异步操作的处理。 错误处理过程中的以下方法可以生成此事件： 
    
   - [IMAPITable::SortTable](imapitable-sorttable.md)
    
   - [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
   - [IMAPITable::Restrict](imapitable-restrict.md)
    
   接收 TABLE_ERROR 事件之后, 客户端不能依赖目录的准确性。 此外，待处理的有关其他更改的通知可能会丢失。 [IMAPITable::GetLastError](imapitable-getlasterror.md)方法可能提供有关错误的任何其他信息，因为它已生成以前点，不一定是从最后一个方法调用。 
    
TABLE_RELOAD 
  
> 应重新加载表中的数据。 服务提供商发送 TABLE_RELOAD 时，例如，基础数据存储在数据库和数据库已替换为。 假定 nothing 有关表是仍然有效和重新读取表处理此事件。 所有书签、 实例项、 状态和位置信息都是无效。
    
TABLE_RESTRICT_DONE 
  
> 启动**IMAPITable::Restrict**方法调用的限制操作已完成。 
    
TABLE_ROW_ADDED 
  
> 新行已添加到表并保存相应对象。 调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法后会生成 TABLE_ROW_ADDED 事件。 
    
TABLE_ROW_DELETED 
  
> 从表中已被删除行。 **PropPrior**成员设置为 NULL。 
    
TABLE_ROW_MODIFIED 
  
> 已更改的行。 **行**成员包含行受影响的属性。 多个 TABLE_ROW_MODIFIED 事件发送它们在表视图中显示的顺序。 
    
  TABLE_ROW_MODIFIED 事件发送后已经与调用**IMAPIProp::SaveChanges**方法提交到相应的对象的更改。 如果已修改的行现在是表中的第一行， **propPrior**成员中的属性标记的值为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。
    
TABLE_SETCOL_DONE 
  
> 启动**IMAPITable::SetColumns**方法调用列设置操作已完成。 
    
TABLE_SORT_DONE 
  
> 已完成，表的排序操作启动**IMAPITable::SortTable**方法调用。 
    
**hResult**
  
> 如果设置为 TABLE_ERROR **ulTableEvent**成员已发生的错误的 HRESULT 值。 
    
**propIndex**
  
> 受影响的行的**PR_INSTANCE_KEY**属性的[SPropValue](spropvalue.md)结构。 
    
**propPrior**
  
> 受影响的一个之前的行的**PR_INSTANCE_KEY**属性**SPropValue**结构。 如果受影响的行，表中的第一行**propPrior**必须设置为**PR_NULL**和不为零。 零不是有效属性标记。 
    
**行**
  
> [SRow](srow.md)结构，描述受影响的行。 为所有表通知事件填充该结构。 对于不传递行数据的表通知事件， **SRow**结构的**cValues**成员设置为零， **lpProps**成员设置为 NULL。 因为此**SRow**结构是只读的。如果他们想要进行修改，客户端必须创建它的一个副本。 [ScDupPropset](scduppropset.md)函数可用于创建副本。 
    
## <a name="remarks"></a>备注

**表\_通知**结构是结构[通知](notification.md)结构的**信息**成员中包含的联合的成员之一。 **Info**成员包括**表\_通知**结构结构中的**ulEventType**成员设置为_fnevTableModified_时。
  
顺序和行成员中的列类型反映的顺序和生效时所处的生成通知的类型。 顺序和时生成通知的类型不一定相同时通知已送达。 
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持的事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用**IMAPISupport**方法生成通知。  <br/> |
   
表通知是异步的因为客户端可以接收有关通过其他方式添加学习之后添加一行的通知。 可以接收 TABLE_ERROR 事件在**IMAPITable::Sort**、 **IMAPITable::Restrict**或**IMAPITable::SetColumns**方法时出现错误或进程时基础尝试更新一个表格，例如，新时或修改后的行。 
  
## <a name="see-also"></a>另请参阅

- [通知](notification.md) 
- [ScDupPropset](scduppropset.md)
- [SRow](srow.md)
- [SPropValue](spropvalue.md)
- [MAPI 结构](mapi-structures.md)

