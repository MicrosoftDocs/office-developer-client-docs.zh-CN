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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415955"
---
# <a name="table_notification"></a>TABLE_NOTIFICATION

**适用于**：Outlook 2013 | Outlook 2016 
  
描述表中受某种类型事件（如更改或错误）影响的行。 这将导致生成表通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 用于表示表事件类型的标志的位掩码。 可以设置以下标志：
    
TABLE_CHANGED 
  
> 在高级别上指示有关表的一些内容已更改。 表的状态与事件之前的状态一样。 这意味着所有 PR_INSTANCE_KEY  ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 、书签、当前位置和用户界面选择都仍然有效。 通过重新读取表来处理此事件。 不希望实现富表通知的服务提供商会TABLE_CHANGED事件而不是更详细的事件来指示特定类型的更改。 
    
TABLE_ERROR 
  
> 通常在处理异步操作期间发生错误。 处理以下方法时出错可能会生成此事件： 
    
   - [IMAPITable::SortTable](imapitable-sorttable.md)
    
   - [IMAPITable::SetColumns](imapitable-setcolumns.md)
    
   - [IMAPITable::Restrict](imapitable-restrict.md)
    
   收到TABLE_ERROR事件后，客户端无法依赖于表内容的准确性。 此外，有关其他更改的挂起通知可能会丢失。 [IMAPITable：：GetLastError](imapitable-getlasterror.md)方法可能不会提供有关该错误的任何附加信息，因为它是在上一个时间点生成的，不一定是上一个方法调用生成的。 
    
TABLE_RELOAD 
  
> 应重新加载表中的数据。 例如，TABLE_RELOAD在数据库中存储基础数据并替换数据库时，服务提供商会发送数据。 通过假定表没有任何信息仍然有效，然后重新读取表来处理此事件。 所有书签、实例键、状态和位置信息均无效。
    
TABLE_RESTRICT_DONE 
  
> 使用 **IMAPITable：：Restrict** 方法调用启动的限制操作已完成。 
    
TABLE_ROW_ADDED 
  
> 新行已添加到表中并保存相应的对象。 TABLE_ROW_ADDED [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法调用后，将生成事件。 
    
TABLE_ROW_DELETED 
  
> 已从表格中删除一行。 **propPrior** 成员设置为 NULL。 
    
TABLE_ROW_MODIFIED 
  
> 行已更改。 行 **成员** 包含行受影响的属性。 多个TABLE_ROW_MODIFIED事件按它们在表视图中的显示顺序发送。 
    
  TABLE_ROW_MODIFIED对相应对象的更改后，通过调用 **IMAPIProp：：SaveChanges** 方法发送事件。 如果修改的行现在是表格中的第一行，**则 propPrior** 成员中的属性标记值PR_NULL ( [PidTagNull](pidtagnull-canonical-property.md)) 。
    
TABLE_SETCOL_DONE 
  
> 使用 **IMAPITable：：SetColumns** 方法调用启动的列设置操作已完成。 
    
TABLE_SORT_DONE 
  
> 已完成使用 **IMAPITable：：SortTable** 方法调用启动的表排序操作。 
    
**hResult**
  
> 如果 **ulTableEvent** 成员设置为活动状态，则已发生错误的 HRESULT TABLE_ERROR。 
    
**propIndex**
  
> 受影响行的 PR_INSTANCE_KEY **属性的** [SPropValue](spropvalue.md)结构。 
    
**propPrior**
  
> 受影响行之前PR_INSTANCE_KEY属性的 **SPropValue** 结构。 如果受影响的行是表格中的第一行 **，propPrior** 必须设置为 **PR_NULL而不是零** 。 零不是有效的属性标记。 
    
**row**
  
> 描述受影响行的[SRow](srow.md)结构。 此结构用于所有表通知事件。 对于不传递行数据的表通知事件 **，SRow** 结构的 **cValues** 成员设置为零 **，lpProps** 成员设置为 NULL。 因为此 **SRow** 结构是只读的;客户端必须创建一个副本，以进行修改。 [ScDupPropset](scduppropset.md)函数可用于创建副本。 
    
## <a name="remarks"></a>备注

**TABLE \_ NOTIFICATION** 结构是 NOTIFICATION 结构的信息成员中包含的结构联合 [的成员](notification.md)之一。 当 **结构的** **ulEventType** 成员设置为 _fnevTableModified_ 时，信息成员包括 TABLE NOTIFICATION 结构。 **\_**
  
行成员中列的顺序和类型反映生成通知时生效的顺序和类型。 生成通知时的顺序和类型不一定与通知送达时相同。 
  
有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 **IMAPISupport** 方法生成通知。  <br/> |
   
由于表通知是异步的，因此客户端可以在通过其他方式了解添加内容后收到添加行的通知。 当 **IMAPITable：：Sort** **、IMAPITable：：Restrict** 或 **IMAPITable：：SetColumns** 方法出错时，或者当基础进程尝试使用新的或修改的行更新表时，可能会收到 TABLE_ERROR 事件。 
  
## <a name="see-also"></a>另请参阅

- [NOTIFICATION](notification.md) 
- [ScDupPropset](scduppropset.md)
- [SRow](srow.md)
- [SPropValue](spropvalue.md)
- [MAPI 结构](mapi-structures.md)

