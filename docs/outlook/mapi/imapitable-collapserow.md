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
ms.openlocfilehash: b4dd7e9715c2d3c99eda44f7eed0b3360a2e33be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595298"
---
# <a name="imapitablecollapserow"></a>IMAPITable::CollapseRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
折叠的扩展的表类别，删除任何级别较低的标题和叶行属于表视图中的类别。
  
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
  
> [in]_PbInstanceKey_参数指向的 PR_INSTANCE_KEY 属性中的字节数。 
    
 _pbInstanceKey_
  
> [in]一个指向标识类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lpulRowCount_
  
> [输出]一个指向正在删除表视图中的行的总数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 折叠操作已成功。
    
MAPI_E_NOT_FOUND 
  
> _PbInstanceKey_参数标识的行不存在。 
    
MAPI_E_INVALID_ENTRYID 
  
> _PbInstanceKey_参数标识的行不存在。 此错误是 MAPI_E_NOT_FOUND; 替代方法服务提供商可以返回其中任何一个。 
    
## <a name="remarks"></a>注解

**IMAPITable::CollapseRow**方法折叠表类别，并将其删除表视图中。 行折叠开始_pbInstanceKey_参数指向**PR_INSTANCE_KEY**属性标识的行。 从视图中删除的行数返回_lpulRowCount_参数的内容。 
  
从视图中删除折叠操作的结果的表格行的永远不会生成通知。 
  
时由书签定义行折叠视图，该书签会移到下一个可见行指向。 
  
有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::DoExpandCollapse  <br/> |MFCMAPI 使用**IMAPITable::CollapseRow**方法折叠表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

