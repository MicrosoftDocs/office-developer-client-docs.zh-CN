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
ms.openlocfilehash: ce78c6873f3a1dc034ae33f3c9e965ef8f2f1815
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563777"
---
# <a name="imapitableexpandrow"></a>IMAPITable::ExpandRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
展开折叠的表类别，添加叶或属于到表视图类别的级别较低的标题行。
  
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
  
> [in]_PbInstanceKey_参数指向的 PR_INSTANCE_KEY 属性中的字节数。 
    
 _pbInstanceKey_
  
> [in]一个指向标识类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 
    
 _ulRowCount_
  
> [in]最大_lppRows_参数中返回的行数。 
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lppRows_
  
> [输出]指向接收已插入到由于扩展表视图的第一个 （最多_ulRowCount_) 行的[SRowSet](srowset.md)结构的指针。 _PbInstanceKey_参数标识的标题行后面插入这些行。 如果_ulRowCount_参数为零，则_lppRows_参数可以为 NULL。 
    
 _lpulMoreRows_
  
> [输出]一个指向已添加到表视图的行的总数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功展开类别。
    
MAPI_E_NOT_FOUND 
  
> _PbInstanceKey_参数标识的行不存在。 
    
## <a name="remarks"></a>注解

**IMAPITable::ExpandRow**方法扩展折叠的表类别，添加叶或属于到表视图类别的级别较低的标题行。 可以_ulRowCount_参数中指定的_lppRows_参数中要返回的行数限制。 时_ulRowCount_设置为的值大于零，由_lppRows_指向在行集中返回一个或多个行集 BOOKMARK_CURRENT 移至紧挨行中的最后一行的行的书签的位置。
  
当_ulRowCount_设置为零，请求的零叶或较低级别标题行添加到该类别中，或不返回零行，因为没有叶或类别中的级别较低的标题行时，到行集 BOOKMARK_CURRENT 的位置关注由_pbInstanceKey_标识的行。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

不会生成通知添加到类别扩展由于表视图的行上。
  
## <a name="notes-to-callers"></a>给调用方的说明

_LppRows_参数指向在行集中的行数不一定等于的实际已添加到表的行数，整个设置的叶或较低级别标题行类别。 发生错误，例如内存不足或超出_ulRowCount_参数中指定的号码的类别中的行数。 在任一情况下，BOOKMARK_CURRENT 将放置在返回的最后一行。 若要立即检索其余的类别中的行，调用[IMAPITable::QueryRows](imapitable-queryrows.md)。
  
不希望类别更改其状态时收到表通知。 您可以维护本地缓存可以与每个**ExpandRow**或**CollapseRow**呼叫更新的行。 
  
有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::DoExpandCollapse  <br/> |MFCMAPI 使用**IMAPITable::ExpandRow**方法以展开折叠的表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CollapseRow](imapitable-collapserow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

