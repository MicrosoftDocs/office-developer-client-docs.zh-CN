---
title: IMAPITableExpandRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.ExpandRow
api_type:
- COM
ms.assetid: b96dd8f6-e648-4014-8a1d-ae1da771c439
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e2ce756baaefef7bd0028e746b1dbe10756365e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415164"
---
# <a name="imapitableexpandrow"></a>IMAPITable::ExpandRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
展开折叠的表类别，将属于该类别的叶标题行或较低级别标题行添加到表视图中。
  
```cpp
HRESULT ExpandRow(
ULONG cbInstanceKey,
LPBYTE pbInstanceKey,
ULONG ulRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows,
ULONG FAR * lpulMoreRows
);
```

## <a name="parameters"></a>参数

 _cbInstanceKey_
  
> [in]  _pbInstanceKey_ 参数PR_INSTANCE_KEY属性中的字节数。 
    
 _pbInstanceKey_
  
> [in]指向标识类别 **的标题** PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的指针。 
    
 _ulRowCount_
  
> [in]  _lppRows_ 参数中要返回的最大行数。 
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lppRows_
  
> [out]一个指向 [SRowSet](srowset.md) 结构的指针，该结构接收 (展开时已插入到表视图中的第一)  _ulRowCount_) 行。 这些行插入到由  _pbInstanceKey_ 参数标识的标题行之后。 如果 ulRowCount 参数为零，则 _lppRows_ 参数可以是 NULL。  
    
 _lpulMoreRows_
  
> [out]指向已添加到表视图的行的总数指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功扩展类别。
    
MAPI_E_NOT_FOUND 
  
> _pbInstanceKey_ 参数标识的行不存在。 
    
## <a name="remarks"></a>备注

**IMAPITable：：ExpandRow** 方法展开折叠的表类别，将属于该类别的叶或较低级别标题行添加到表视图。 可以在 _ulRowCount_ 参数中指定 _对在 lppRows_ 参数中返回的行数的限制。 当  _ulRowCount_ 设置为大于零的值，并且  _lppRows_ 指向的行集返回一行或多行时，书签 BOOKMARK_CURRENT 的位置将移动到紧随行集最后一行的行。
  
当  _ulRowCount_ 设置为零时，请求将零叶或较低级别的标题行添加到类别中，或者返回零行，因为类别中没有叶标题行或较低级别标题行，BOOKMARK_CURRENT 的位置将设置为  _pbInstanceKey_ 标识的行后行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

请勿在因类别扩展而添加到表视图中的行上生成通知。
  
## <a name="notes-to-callers"></a>给调用方的说明

_lppRows_ 参数指向的行集的行数可能并不等于实际添加到表中的行数，即类别的整组叶标题行或较低级别标题行。 可能会发生错误，例如内存不足或类别中的行数超过  _ulRowCount_ 参数中指定的行数。 在任一情况下，BOOKMARK_CURRENT将位于返回的最后一行。 若要立即检索类别中的其余行，请调用 [IMAPITable：：QueryRows](imapitable-queryrows.md)。
  
当类别更改其状态时，不要收到表通知。 您可以维护可通过每个 **ExpandRow** 或 **CollapseRow** 调用更新的行的本地缓存。 
  
有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：:D oExpandCollapse  <br/> |MFCMAPI 使用 **IMAPITable：：ExpandRow** 方法展开折叠的表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CollapseRow](imapitable-collapserow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

