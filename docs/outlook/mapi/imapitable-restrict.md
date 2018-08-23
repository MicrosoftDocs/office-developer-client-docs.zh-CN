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
ms.openlocfilehash: 924715f26e104739f2e60762511221da5facd5a5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578323"
---
# <a name="imapitablerestrict"></a>IMAPITable::Restrict

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
筛选器应用于表格，从而减少了设置为仅与指定的条件匹配这些行的行。
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]定义筛选器的条件[SRestriction](srestriction.md)结构的指针。 传递 NULL _lpRestriction_参数中删除当前的筛选器。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制限制操作的时间。 可以设置以下标志：
    
TBL_ASYNC 
  
> 异步启动操作并返回之前操作完成。
    
TBL_BATCH 
  
> 延迟的筛选器评估，直到表中的数据，则需要。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功应用筛选器。
    
MAPI_E_BUSY 
  
> 阻止限制操作启动的正在进行中是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_TOO_COMPLEX 
  
> 表无法执行操作，因为太复杂_lpRestriction_参数指向特定筛选器。 
    
## <a name="remarks"></a>注解

**IMAPITable::Restrict**方法建立的限制或筛选，请在表。 如果没有前面限制，则它会丢弃并新建一个应用。 应用了限制对基础数据的表; 没有影响它只会改变视图通过限制可以检索到包含满足在限制的数据行的行。 
  
有几种不同类型的限制，每个具有不同结构所述。 [SRestriction](srestriction.md)结构包含两个成员： 一个值，指示限制和适用于该类型的特定结构的类型。 
  
永远不会生成的已**Restrict**呼叫被隐藏视图中的表格行的通知。 
  
对多值属性的属性限制的工作方式类似的单值属性限制。 在属性限制中使用的多值的属性必须设置 MVI_FLAG 标志。 如果它没有设置此标志，则将其视为完全有序元组。 两个多值列的比较比较中报告的第一个不相等中的列的关系的顺序的列元素。 仅当比较的列包含相同的顺序相同的值，则返回相等。 如果一个列具有比其他值少，报告的关系是 null 值为其他值。
  
有关限制的详细信息，请参阅[有关限制](about-restrictions.md)。
  
> [!NOTE]
> 如果您创建动态查询搜索服务器上的数据，而不是使用**Restrict**方法和**QueryRows**方法一起使用**FindRow**方法。 **Restrict**方法创建的用于评估添加或修改的基文件夹中的所有邮件缓存的视图。 如果客户端应用程序的每个动态查询使用**Restrict**方法，将创建每个查询的缓存的视图。 
  
## <a name="notes-to-callers"></a>给调用方的说明

放弃而无需创建一个新的当前限制，请在_lpRestriction_传递 NULL。
  
如果另一个异步表呼叫正在进行，导致**Restrict**返回 MAPI_E_BUSY，您可以调用[IMAPITable::Abort](imapitable-abort.md)停止呼叫。 
  
 除非将其中一个标志设置**限制**进行同步操作。 如果设置 TBL_BATCH 标志， **Restrict**推迟评估版的限制，除非您请求的数据。 如果设置 TBL_ASYNC 标志，则**Restrict**操作以异步方式，可能返回之前完成操作。
  
当调用**Restrict**不进行，并且 BOOKMARK_CURRENT，当前光标位置，设置为表的开头，则将被丢弃的表的所有书签。 
  
如果尝试为多少属性限制中表的列集不是一个属性，则结果是未定义。 只要您不确定来对属性的表中是否受支持，结合使用属性限制存在限制。 存在限制检查尝试实施属性限制之前的属性是否存在。 
  
不希望接收由于限制表中的已筛选的行上的表通知。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::ApplyRestriction  <br/> |MFCMAPI 使用**IMAPITable::Restrict**方法在表上设置限制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::Abort](imapitable-abort.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

