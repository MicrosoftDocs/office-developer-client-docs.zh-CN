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
ms.openlocfilehash: 86dfaa8fbc9ff24d38472f1339a22534086d890b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593744"
---
# <a name="imapitablequerycolumns"></a>IMAPITable::QueryColumns

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回表格列的列表。
  
```cpp
HRESULT QueryColumns(
ULONG ulFlags,
LPSPropTagArray FAR * lpPropTagArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]应返回的标志，指示哪些列设置的位掩码。 可以设置以下标记：
    
TBL_ALL_COLUMNS 
  
> 表应返回所有可用的列。
    
 _lpPropTagArray_
  
> [输出]指向包含属性标记为列[SPropTagArray](sproptagarray.md)结构设置。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回列集。
    
MAPI_E_BUSY 
  
> 另一个操作阻止列的正在进行中设置启动的检索操作。 应允许正在进行的操作完成或应停止。
    
## <a name="remarks"></a>注解

**IMAPITable::QueryColumns**方法可调用它以检索： 
  
- 为表设置默认列。
    
- 由调用[IMAPITable::SetColumns](imapitable-setcolumns.md)方法建立为表，设置当前列。 
    
- 完整的列设置的表、 列可用，而不是一定是当前集的一部分。
    
## <a name="notes-to-callers"></a>给调用方的说明

如果未设置 TBL_ALL_COLUMNS 标志， **IMAPITable::QueryColumns**返回表的默认或当前列集，具体取决于是否表已经受到**IMAPITable::SetColumns**调用。 **SetColumns**更改顺序和所选内容中表的列集的列。 
  
如果设置 TBL_ALL_COLUMNS 标志， **QueryColumns**返回的所有能够在表的列组列。 
  
释放内存为通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数_lpPropTagArray_参数指向的属性标记数组。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::DoSetColumns  <br/> |MFCMAPI 使用**IMAPITable::QueryColumns**方法检索当前为表设置，以便用户可以编辑的列。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

