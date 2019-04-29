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
  
将筛选器应用于表, 将行设置为仅将行设置为与指定条件匹配的行。
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> 实时指向定义筛选条件的[SRestriction](srestriction.md)结构的指针。 在_lpRestriction_参数中传递 NULL 将删除当前的筛选器。 
    
 _ulFlags_
  
> 实时控制限制操作的时间的标志的位掩码。 可以设置以下标志:
    
TBL_ASYNC 
  
> 异步启动操作并在操作完成前返回。
    
TBL_BATCH 
  
> 推迟对筛选器的求值, 直到表中的数据是必需的。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功应用筛选器。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止启动限制操作。 应允许正在进行的操作完成, 或者应已停止。
    
MAPI_E_TOO_COMPLEX 
  
> 表无法执行此操作, 因为_lpRestriction_参数指向的特定筛选器过于复杂。 
    
## <a name="remarks"></a>说明

**IMAPITable:: Restrict**方法在表上建立限制或筛选器。 如果存在以前的限制, 将丢弃它并应用新的限制。 应用限制对表的基础数据没有影响。它只是通过限制可检索到包含满足限制的数据的行的行来更改视图。 
  
有几种不同类型的限制, 每种类型都有不同的结构说明。 [SRestriction](srestriction.md)结构包含两个成员: 一个值, 该值指示限制的类型以及适用于该类型的特定结构。 
  
从不生成通过对**Restrict**的调用而隐藏的表行的通知。 
  
对多值属性的属性限制的工作方式类似于对单值属性的限制。 要在属性限制中使用的多值属性必须设置 MVI_FLAG 标志。 如果未设置此标志, 则会将其视为一个完全排序的元组。 两个多值列的比较将按顺序对列元素进行比较, 报告第一个不相等的列关系。 仅当列的比较包含相同顺序的相同值时, 才返回相等性。 如果某一列的值少于其他列的值, 则报告的关系为将 null 值的其他值。
  
有关限制的详细信息, 请参阅[关于限制](about-restrictions.md)。
  
> [!NOTE]
> 如果创建动态查询以在服务器上搜索数据, 请使用**FindRow**方法, 而不是将**Restrict**方法和**QueryRows**方法一起使用。 **Restrict**方法创建一个缓存视图, 用于评估在基文件夹中添加或修改的所有邮件。 如果客户端应用程序对每个动态查询使用**Restrict**方法, 则将为每个查询创建一个缓存视图。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要在不创建新限制的情况下放弃当前限制, 请在_lpRestriction_中传递 NULL。
  
如果正在进行另一个异步表调用, 从而导致**限制**返回 MAPI_E_BUSY, 则可以调用[IMAPITable:: Abort](imapitable-abort.md)停止呼叫。 
  
 **限制**同步操作, 除非您设置了其中一个标志。 如果设置了 TBL_BATCH 标志, 则**限制**推迟对限制的评估, 除非您请求数据。 如果设置了 TBL_ASYNC 标志, 则**限制**在完成操作之前异步操作, 可能会返回。
  
表的所有书签都会在进行**限制**调用时被丢弃, 而将 BOOKMARK_CURRENT 的当前光标位置设置为表的开头。 
  
如果尝试对不在表的列集中的属性施加属性限制, 则结果是不确定的。 只要您不确定某个属性是否在表中受支持, 请将该属性限制与存在的限制组合在一起。 在尝试强制实施属性限制之前, 存在限制会检查是否存在该属性。 
  
如果由于限制而从表中筛选出的行上不应收到表通知。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl:: ApplyRestriction  <br/> |MFCMAPI 使用**IMAPITable:: Restrict**方法来设置对表的限制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::Abort](imapitable-abort.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

