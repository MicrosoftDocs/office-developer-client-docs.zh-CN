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
ms.openlocfilehash: cda3de1719ec1b7cfca1a9ecdad7bc3b59a8b17d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571148"
---
# <a name="imapitablegetstatus"></a>IMAPITable::GetStatus

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回表的状态和类型。
  
```cpp
HRESULT GetStatus(
ULONG FAR * lpulTableStatus,
ULONG FAR * lpulTableType
);
```

## <a name="parameters"></a>参数

 _lpulTableStatus_
  
> [输出]指向一个值，该值表的状态。 可以返回下列值之一：
    
TBLSTAT_COMPLETE 
  
> 不正在执行任何操作。
    
TBLSTAT_QCHANGED 
  
> Expectantly 已更改的表的内容。 此状态值不会返回的结果排序或限制的操作的更改。
    
TBLSTAT_RESTRICT_ERROR 
  
> [IMAPITable::Restrict](imapitable-restrict.md)操作过程中出错。 
    
TBLSTAT_RESTRICTING 
  
> 正在**IMAPITable::Restrict**操作。 
    
TBLSTAT_SETCOL_ERROR 
  
> [IMAPITable::SetColumns](imapitable-setcolumns.md)操作过程中出错。 
    
TBLSTAT_SETTING_COLS 
  
> 正在**IMAPITable::SetColumns**操作。 
    
TBLSTAT_SORT_ERROR 
  
> [IMAPITable::SortTable](imapitable-sorttable.md)操作过程中出错。 
    
TBLSTAT_SORTING 
  
> 正在**IMAPITable::SortTable**操作。 
    
 _lpulTableType_
  
> [输出]指向一个值，指示表的类型。 可以返回以下三个表类型之一：
    
TBLTYPE_DYNAMIC 
  
> 表的内容是动态;行和列的值可以更改基础数据集更改。
    
TBLTYPE_KEYSET 
  
> 表中的行固定的但这些行中的列的值动态，并可以更改基础数据集更改。
    
TBLTYPE_SNAPSHOT 
  
> 表是静态的而在基础数据更改时不更改其内容。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回表的状态。
    
## <a name="remarks"></a>注解

**IMAPTable::GetStatus**方法检索有关表的类型和当前状态信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可用于**GetStatus**结合使用三种其他**IMAPITable**方法以监视这些操作的状态，并确定表的效果。 呼叫**GetStatus**后使下面的**IMAPITable**调用之一： 
  
- [IMAPITable::Restrict](imapitable-restrict.md)设置限制。 
    
- [IMAPITable::SortTable](imapitable-sorttable.md)建立排序顺序。 
    
- [IMAPITable::SetColumns](imapitable-setcolumns.md)定义一列。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::GetStatus  <br/> |MFCMAPI 使用**IMAPITable::GetStatus**方法报告表的状态。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

