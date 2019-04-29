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
  
返回表的列的列表。
  
```cpp
HRESULT QueryColumns(
ULONG ulFlags,
LPSPropTagArray FAR * lpPropTagArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时指示应返回哪一列集的标志的位掩码。 可以设置以下标志:
    
TBL_ALL_COLUMNS 
  
> 该表应返回所有可用的列。
    
 _lpPropTagArray_
  
> 排除指向包含列集的属性标记的[SPropTagArray](sproptagarray.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回列集。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以防止启动列集检索操作。 应允许正在进行的操作完成, 或者应已停止。
    
## <a name="remarks"></a>说明

可以调用**IMAPITable:: QueryColumns**方法来检索: 
  
- 为表格设置的默认列。
    
- 为表设置的当前列, 这是通过调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法建立的。 
    
- 表的完整列集、可用的列, 但不一定是当前集合的一部分。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果未设置 TBL_ALL_COLUMNS 标志, 则**IMAPITable:: QueryColumns**将返回表的默认值或当前列集, 具体取决于表是否受到对**IMAPITable:: SetColumns**的调用的影响。 **SetColumns**更改表的列集合中列的顺序和选择。 
  
如果设置 TBL_ALL_COLUMNS 标志, 则**QueryColumns**将返回能够在表的列集中进行的所有列。 
  
通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 释放由_lpPropTagArray_参数指向的属性标记数组的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl::D osetcolumns  <br/> |MFCMAPI 使用**IMAPITable:: QueryColumns**方法检索表的当前列集, 以便用户可以对其进行编辑。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

