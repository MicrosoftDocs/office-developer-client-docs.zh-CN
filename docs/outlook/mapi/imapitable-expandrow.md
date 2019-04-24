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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329038"
---
# <a name="imapitableexpandrow"></a>IMAPITable::ExpandRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
展开折叠的表格类别, 将属于该类别的叶片或下层标题行添加到表格视图中。
  
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
  
> 实时_pbInstanceKey_参数所指向的 PR_INSTANCE_KEY 属性中的字节数。 
    
 _pbInstanceKey_
  
> 实时一个指针, 指向用于标识该类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 
    
 _ulRowCount_
  
> 实时要在_lppRows_参数中返回的最大行数。 
    
 _ulFlags_
  
> 保留必须为零。
    
 _lppRows_
  
> 排除指向接收第一个 (最多为_ulRowCount_) 行的[SRowSet](srowset.md)结构的指针, 这些行是由于扩展而插入到表视图中的。 这些行在_pbInstanceKey_参数所标识的标题行后插入。 如果_ulRowCount_参数为零, 则_lppRows_参数可以为 NULL。 
    
 _lpulMoreRows_
  
> 排除一个指针, 指向已添加到表视图中的总行数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 类别已成功扩展。
    
MAPI_E_NOT_FOUND 
  
> 由_pbInstanceKey_参数标识的行不存在。 
    
## <a name="remarks"></a>注解

**IMAPITable:: ExpandRow**方法展开一个折叠的表类别, 将属于该类别的叶或低级标题行添加到表视图中。 可以在_ulRowCount_参数中指定对_lppRows_参数中要返回的行数的限制。 如果将_ulRowCount_设置为大于零的值, 并且在_lppRows_指向的行集中返回一个或多个行, 则书签 BOOKMARK_CURRENT 的位置将移至紧跟在行集中最后一行后面的行。
  
如果将_ulRowCount_设置为零, 请求将零点或较低级别的标题行添加到类别中, 或由于类别中没有叶或低级标题行而返回零行, 则 BOOKMARK_CURRENT 的位置将设置为行。关注由_pbInstanceKey_标识的行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

请勿在由于类别扩展而添加到表视图中的行上生成通知。
  
## <a name="notes-to-callers"></a>给调用方的说明

由_lppRows_参数指向的行集内的行数可能不等于实际添加到表中的行数, 即类别的整个叶或低级标题行的数目。 错误可能会发生, 如内存不足, 或超出_ulRowCount_参数中指定的数字的类别中的行数。 在这两种情况下, BOOKMARK_CURRENT 将放置在返回的最后一行上。 若要立即检索类别中的其余行, 请调用[IMAPITable:: QueryRows](imapitable-queryrows.md)。
  
不希望在类别更改其状态时收到表格通知。 您可以维护可使用每个**ExpandRow**或**CollapseRow**调用更新的行的本地缓存。 
  
有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl::D oexpandcollapse  <br/> |MFCMAPI 使用**IMAPITable:: ExpandRow**方法展开折叠的表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CollapseRow](imapitable-collapserow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

