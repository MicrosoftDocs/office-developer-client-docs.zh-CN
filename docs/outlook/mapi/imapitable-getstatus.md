---
title: IMAPITableGetStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetStatus
api_type:
- COM
ms.assetid: f114f1fa-bc05-4587-875b-71548c5912ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec305fc872d1bf1718592dabdd230617d50d3f54
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434331"
---
# <a name="imapitablegetstatus"></a>IMAPITable::GetStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回表的状态和类型。
  
```cpp
HRESULT GetStatus(
ULONG FAR * lpulTableStatus,
ULONG FAR * lpulTableType
);
```

## <a name="parameters"></a>参数

 _lpulTableStatus_
  
> 排除指向一个指示表状态的值的指针。 可以返回下列值之一:
    
TBLSTAT_COMPLETE 
  
> 没有正在进行的操作。
    
TBLSTAT_QCHANGED 
  
> 表的内容已更改 expectantly。 对于由排序或限制操作导致的更改, 不会返回此状态值。
    
TBLSTAT_RESTRICT_ERROR 
  
> [IMAPITable:: Restrict](imapitable-restrict.md)操作期间发生错误。 
    
TBLSTAT_RESTRICTING 
  
> **IMAPITable:: Restrict**操作正在进行中。 
    
TBLSTAT_SETCOL_ERROR 
  
> [IMAPITable:: SetColumns](imapitable-setcolumns.md)操作期间发生错误。 
    
TBLSTAT_SETTING_COLS 
  
> **IMAPITable:: SetColumns**操作正在进行中。 
    
TBLSTAT_SORT_ERROR 
  
> [IMAPITable:: SortTable](imapitable-sorttable.md)操作期间发生错误。 
    
TBLSTAT_SORTING 
  
> **IMAPITable:: SortTable**操作正在进行中。 
    
 _lpulTableType_
  
> 排除指向指示表的类型的值的指针。 可以返回以下三种表格类型之一:
    
TBLTYPE_DYNAMIC 
  
> 表的内容是动态的;行和列的值会随着基础数据的变化而变化。
    
TBLTYPE_KEYSET 
  
> 表中的行是固定的, 但这些行中的列的值是动态的, 并且可以随着基础数据的变化而变化。
    
TBLTYPE_SNAPSHOT 
  
> 该表是静态的, 并且在基础数据发生更改时它的内容不会更改。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回表的状态。
    
## <a name="remarks"></a>说明

**IMAPTable:: GetStatus**方法检索有关表的类型和当前状态的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以将**GetStatus**与其他三个**IMAPITable**方法结合使用, 以监视这些操作的状态并确定对表的影响。 在进行以下**IMAPITable**调用之一后调用**GetStatus** : 
  
- [IMAPITable:: Restrict](imapitable-restrict.md)设置限制。 
    
- [IMAPITable:: SortTable](imapitable-sorttable.md)以建立排序顺序。 
    
- [IMAPITable:: SetColumns](imapitable-setcolumns.md)定义列集。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl:: GetStatus  <br/> |MFCMAPI 使用**IMAPITable:: GetStatus**方法报告表的状态。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

