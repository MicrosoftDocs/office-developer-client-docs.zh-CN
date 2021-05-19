---
title: IMAPITableRestrict
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Restrict
api_type:
- COM
ms.assetid: a5bfc190-b58f-44c3-893c-8727df14ee58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cca6bc12fa6f100885b7bf705d79fa24a2e2f91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414618"
---
# <a name="imapitablerestrict"></a>IMAPITable::Restrict

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将筛选器应用于表，从而将行设置为仅与指定条件匹配的行。
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]指向定义 [筛选器条件的 SRestriction](srestriction.md) 结构的指针。 在  _lpRestriction_ 参数中传递 NULL 将删除当前筛选器。 
    
 _ulFlags_
  
> [in]控制限制操作计时的标志的位掩码。 可以设置以下标志：
    
TBL_ASYNC 
  
> 异步启动操作，在操作完成之前返回。
    
TBL_BATCH 
  
> 延迟对筛选器的评估，直到需要表中的数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功应用筛选器。
    
MAPI_E_BUSY 
  
> 正在进行另一个阻止限制操作启动的操作。 应允许完成或停止进行中的操作。
    
MAPI_E_TOO_COMPLEX 
  
> 表无法执行该操作，因为  _lpRestriction_ 参数指向的特定筛选器过于复杂。 
    
## <a name="remarks"></a>备注

**IMAPITable：：Restrict** 方法在表上建立限制或筛选器。 如果存在以前的限制，则放弃它并应用新的限制。 应用限制不会影响表的基础数据;它只需通过将可检索的行限制到包含满足限制的数据的行来更改视图。 
  
存在几种不同类型的限制，每种限制都使用不同的结构进行描述。 [SRestriction](srestriction.md)结构包含两个成员：一个指示限制类型和适用于该类型的特定结构的值。 
  
从不生成通过调用 Restrict 从视图中隐藏的 **表** 行的通知。 
  
多值属性的属性限制的工作方式与单值属性的限制类似。 要用于属性限制的多值属性必须设置MVI_FLAG标记。 如果未设置此标志，则被视为完全排序的元组。 两个多值列的比较按顺序比较列元素，报告第一个不相等的列的关系。 只有当比较的列包含相同顺序的相同值时，才返回等同性。 如果一列的值数少于另一列的值，则报告的关系为空值与另一个值的关系。
  
有关限制的信息，请参阅关于 [限制](about-restrictions.md)。
  
> [!NOTE]
> 如果创建动态查询以搜索服务器上数据，请使用 **FindRow** 方法，而不是同时使用 **Restrict** 方法和 **QueryRows** 方法。 **Restrict** 方法创建一个缓存视图，该视图用于评估添加到基文件夹中或修改的所有邮件。 如果客户端应用程序针对每个动态查询使用 **Restrict** 方法，将针对每个查询创建缓存视图。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要放弃当前限制而不创建新的限制，请传递  _lpRestriction 中的_ NULL。
  
如果正在进行另一个异步表调用，从而导致 **Restrict** 返回MAPI_E_BUSY，您可以调用 [IMAPITable：：Abort](imapitable-abort.md) 以停止调用。 
  
 **除非** 设置了其中一个标志，否则 Restrict 将同步运行。 如果设置 TBL_BATCH 标志，除非请求数据， **否则 Restrict** 将推迟计算限制。 如果TBL_ASYNC， **则 Restrict** 将异步运行，在操作完成之前可能会返回。
  
当调用 **Restrict** 时，将放弃表的所有书签，BOOKMARK_CURRENT当前光标位置设置为表的开头。 
  
如果您尝试对不在表的列集内的属性施加属性限制，则结果未定义。 只要不确定某个属性在表中是否受支持，就会将属性限制与存在的限制组合在一起。 在试图施加属性限制之前，存在限制会检查属性是否存在。 
  
不要因为限制而收到从表中筛选的行上的表通知。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：：ApplyRestriction  <br/> |MFCMAPI 使用 **IMAPITable：：Restrict** 方法对表设置限制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::Abort](imapitable-abort.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

