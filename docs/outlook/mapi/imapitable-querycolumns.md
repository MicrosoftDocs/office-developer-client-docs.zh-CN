---
title: IMAPITableQueryColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryColumns
api_type:
- COM
ms.assetid: d6341acc-c6ca-4605-93af-77230040339d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d142e19fc4721cec4dde0df7fc030a001121da63
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410103"
---
# <a name="imapitablequerycolumns"></a>IMAPITable::QueryColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回表格的列列表。
  
```cpp
HRESULT QueryColumns(
ULONG ulFlags,
LPSPropTagArray FAR * lpPropTagArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]指示应返回哪一列集的标志的位掩码。 可以设置以下标志：
    
TBL_ALL_COLUMNS 
  
> 该表应返回所有可用列。
    
 _lpPropTagArray_
  
> [out]指向包含列集的属性标记的 [SPropTagArray](sproptagarray.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回列集。
    
MAPI_E_BUSY 
  
> 另一个操作正在进行中，可防止列集检索操作启动。 应允许完成或停止进行中的操作。
    
## <a name="remarks"></a>备注

**可以调用 IMAPITable：：QueryColumns** 方法来检索： 
  
- 表的默认列集。
    
- 表的当前列集，由对 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法的调用建立。 
    
- 表的完整列集（可用列，但不一定是当前集合的一部分）。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果不设置 TBL_ALL_COLUMNS 标志， **则 IMAPITable：：QueryColumns** 将返回表的默认列或当前列集，具体取决于表是否受 **IMAPITable：：SetColumns** 的调用影响。 **SetColumns** 更改表的列集的列的顺序和选择。 
  
如果设置 **TBL_ALL_COLUMNS，QueryColumns** 将返回表的列集内能够包含的所有列。 
  
通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 _lpPropTagArray_ 参数指向的属性标记数组的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：:D oSetColumns  <br/> |MFCMAPI 使用 **IMAPITable：：QueryColumns** 方法来检索表的当前列集，以便用户可以编辑它。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

