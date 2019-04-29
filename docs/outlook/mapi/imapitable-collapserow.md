---
title: IMAPITableCollapseRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.CollapseRow
api_type:
- COM
ms.assetid: 1a23e555-be26-43fb-a715-cfc4ffa623cd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e6a180ceb325a705ebf226bb728c52cce7396490
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416172"
---
# <a name="imapitablecollapserow"></a>IMAPITable::CollapseRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
折叠展开的表格类别, 从表格视图中删除属于该类别的所有低级标题和叶行。
  
```cpp
HRESULT CollapseRow(
ULONG cbInstanceKey,
LPBYTE pbInstanceKey,
ULONG ulFlags,
ULONG FAR * lpulRowCount
);
```

## <a name="parameters"></a>参数

 _cbInstanceKey_
  
> 实时_pbInstanceKey_参数所指向的 PR_INSTANCE_KEY 属性中的字节数。 
    
 _pbInstanceKey_
  
> 实时一个指针, 指向用于标识该类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 
    
 _ulFlags_
  
> 保留必须为零。
    
 _lpulRowCount_
  
> 排除一个指针, 指向要从表视图中删除的总行数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 折叠操作已成功。
    
MAPI_E_NOT_FOUND 
  
> 由_pbInstanceKey_参数标识的行不存在。 
    
MAPI_E_INVALID_ENTRYID 
  
> 由_pbInstanceKey_参数标识的行不存在。 此错误是 MAPI_E_NOT_FOUND 的替代方法;服务提供程序可以返回其中一个。 
    
## <a name="remarks"></a>说明

**IMAPITable:: CollapseRow**方法折叠表类别并将其从表格视图中删除。 行是从由_pbInstanceKey_参数指向的**PR_INSTANCE_KEY**属性所标识的行开始折叠的。 从视图中删除的行数在_lpulRowCount_参数的内容中返回。 
  
从不为作为折叠操作的结果从视图中删除的表行生成通知。 
  
当书签定义的行折叠在视图之外时, 该书签将移到指向下一个可见行的位置。 
  
有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl::D oexpandcollapse  <br/> |MFCMAPI 使用**IMAPITable:: CollapseRow**方法折叠表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

