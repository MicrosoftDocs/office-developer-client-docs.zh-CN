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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6c35220529fb88b470c563a0b004bfcf7e63ef76
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345645"
---
# <a name="tablenotification"></a>TABLE_NOTIFICATION

**适用于**：Outlook 2013 | Outlook 2016 
  
描述已受某种类型的事件 (如更改或错误) 影响的表中的行。 这将导致生成表通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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

## <a name="members"></a>Members

**ulTableEvent**
  
> 用于表示表事件类型的标志的位掩码。 可以设置以下标志:
    
TABLE_CHANGED 
  
> 指示在较高级别上, 关于表的某项已更改。 表的状态与事件之前的状态相同。 这意味着所有**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性、书签、当前定位和用户界面选择仍然有效。 通过并表格处理此事件。 不希望实现丰富表通知的服务提供程序发送 TABLE_CHANGED 事件, 而不是更详细的事件来指示特定类型的更改。 
    
TABLE_ERROR 
  
> 发生错误, 通常是在处理异步操作的过程中。 处理以下方法时出现的错误可能会生成此事件: 
    
   - [IMAPITable::SortTable](imapitable-sorttable.md)
    
   - [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
   - [IMAPITable::Restrict](imapitable-restrict.md)
    
   在接收到 TABLE_ERROR 事件之后, 客户端将无法依赖表内容的准确性。 此外, 有关其他更改的挂起通知可能会丢失。 [IMAPITable:: GetLastError](imapitable-getlasterror.md)方法可能不提供有关错误的任何其他信息, 因为它是在之前的某个点生成的, 而不一定是从最后的方法调用生成的。 
    
TABLE_RELOAD 
  
> 应重新加载表中的数据。 服务提供程序发送 TABLE_RELOAD, 例如, 基础数据存储在数据库中, 而数据库被替换。 通过假定表中的任何内容仍然有效并并表来处理此事件。 所有书签、实例键、状态和定位信息都无效。
    
TABLE_RESTRICT_DONE 
  
> 已完成使用**IMAPITable:: Restrict**方法调用启动的限制操作。 
    
TABLE_ROW_ADDED 
  
> 已将新的行添加到表中, 并保存了对应的对象。 TABLE_ROW_ADDED 事件是在调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之后生成的。 
    
TABLE_ROW_DELETED 
  
> 已从表中删除了行。 **propPrior**成员设置为 NULL。 
    
TABLE_ROW_MODIFIED 
  
> 行已更改。 **行**成员包含受影响的行属性。 多个 TABLE_ROW_MODIFIED 事件按其在表视图中的显示顺序发送。 
    
  在使用对**IMAPIProp:: SaveChanges**方法的调用提交对相应对象的更改之后, 将发送 TABLE_ROW_MODIFIED 事件。 如果已修改的行现在是表中的第一行, 则**propPrior**成员中的属性标记的值是**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。
    
TABLE_SETCOL_DONE 
  
> 已完成使用**IMAPITable:: SetColumns**方法调用启动的列设置操作。 
    
TABLE_SORT_DONE 
  
> 已完成使用**IMAPITable:: SortTable**方法调用启动的表排序操作。 
    
**hResult**
  
> 如果将**ulTableEvent**成员设置为 TABLE_ERROR, 则为已发生的错误的 HRESULT 值。 
    
**propIndex**
  
> 受影响的行的**PR_INSTANCE_KEY**属性的[SPropValue](spropvalue.md)结构。 
    
**propPrior**
  
> 受影响的行前面的**PR_INSTANCE_KEY**属性的**SPropValue**结构。 如果受影响的行是表中的第一行, 则**propPrior**必须设置为**PR_NULL** , 而不是零。 零不是有效的属性标记。 
    
**行**
  
> 描述受影响的行的[SRow](srow.md)结构。 此结构是为所有表通知事件而填充的。 对于不传递行数据的表通知事件, **SRow**结构的**cValues**成员设置为零, **lpProps**成员设置为 NULL。 由于此**SRow**结构是只读的;如果客户端要进行修改, 则必须为其创建副本。 [ScDupPropset](scduppropset.md)函数可用于制作副本。 
    
## <a name="remarks"></a>注解

**表\_通知**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。 当结构的**ulEventType**成员设置为_fnevTableModified_时, **info**成员包含一个**表\_通知**结构。
  
行成员中的列的顺序和类型反映生成通知时有效的顺序和类型。 通知生成时的顺序和类型不一定与传递通知的时间相同。 
  
有关通知的详细信息, 请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论了如何使用**IMAPISupport**方法生成通知的服务提供商。  <br/> |
   
由于表通知是异步的, 因此, 客户端可以在了解通过另一种方法添加的信息后接收已添加的行的通知。 如果**IMAPITable:: Sort**、 **IMAPITable:: Restrict**或**IMAPITable:: SetColumns**方法中出现错误, 或者基础进程尝试更新表 (例如 new 或 TABLE_ERROR), 则可能会收到一个 "" 事件。修改的行。 
  
## <a name="see-also"></a>另请参阅

- [NOTIFICATION](notification.md) 
- [ScDupPropset](scduppropset.md)
- [SRow](srow.md)
- [SPropValue](spropvalue.md)
- [MAPI 结构](mapi-structures.md)

