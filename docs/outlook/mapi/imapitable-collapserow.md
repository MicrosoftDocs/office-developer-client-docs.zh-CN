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
  
折叠展开的表类别，从表视图中删除属于该类别的任何较低级别标题和叶行。
  
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
  
> [in]  _pbInstanceKey_ 参数PR_INSTANCE_KEY属性中的字节数。 
    
 _pbInstanceKey_
  
> [in]指向标识类别 **的标题** PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的指针。 
    
 _ulFlags_
  
> 保留;必须为零。
    
 _lpulRowCount_
  
> [out]指向从表视图中删除的总行数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 折叠操作已成功。
    
MAPI_E_NOT_FOUND 
  
> _pbInstanceKey_ 参数标识的行不存在。 
    
MAPI_E_INVALID_ENTRYID 
  
> _pbInstanceKey_ 参数标识的行不存在。 此错误是一种替代MAPI_E_NOT_FOUND;服务提供程序可以返回其中一个。 
    
## <a name="remarks"></a>备注

**IMAPITable：：CollapseRow** 方法折叠表类别，并从表视图中删除该类别。 从 _pbInstanceKey_ 参数指向的 **PR_INSTANCE_KEY** 属性所标识的行开始折叠行。 从视图中删除的行数在  _lpulRowCount_ 参数的内容中返回。 
  
从不为由于折叠操作而从视图中删除的表行生成通知。 
  
当书签定义的行折叠到视图外时，书签将移动到下一个可见行。 
  
有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：:D oExpandCollapse  <br/> |MFCMAPI 使用 **IMAPITable：：CollapseRow** 方法折叠表类别。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::ExpandRow](imapitable-expandrow.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

