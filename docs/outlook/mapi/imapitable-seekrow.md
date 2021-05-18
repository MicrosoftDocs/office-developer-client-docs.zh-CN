---
title: IMAPITableSeekRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SeekRow
api_type:
- COM
ms.assetid: 93ac63ae-f254-45e1-a9b1-347d69d2ed9f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fbc990a8c962883aa07987b200d1d2fd55434f93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413043"
---
# <a name="imapitableseekrow"></a>IMAPITable::SeekRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将光标移到表格中的特定位置。
  
```cpp
HRESULT SeekRow(
BOOKMARK bkOrigin,
LONG lRowCount,
LONG FAR * lplRowsSought
);
```

## <a name="parameters"></a>参数

 _bkOrigin_
  
> [in]用于标识查找操作起始位置的书签。 可以使用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md) 方法创建书签，也可以传递以下预定义值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表的开头开始查找操作。 
    
BOOKMARK_CURRENT 
  
> 从光标所在的表格中的行开始查找操作。 
    
BOOKMARK_END 
  
> 从表的末尾开始查找操作。 
    
 _lRowCount_
  
> [in]要移动的行数的有签名计数，从  _bkOrigin_ 参数标识的书签开始。 
    
 _lplRowsS以_
  
> [out]如果  _lRowCount_ 是输入上的有效指针  _，lplRowsS此操作_ 将指向在 seek 操作中处理的行数，其符号指示搜索方向、向前或向后方向。 如果  _lRowCount_ 为负数，  _则 lplRowsS以负_ 数表示。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 查找操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作，以防止行寻找操作启动。 应允许完成或停止进行中的操作。
    
MAPI_E_INVALID_BOOKMARK 
  
> _bkOrigin_ 参数中指定的书签无效，因为它已删除或超出了请求的最后一行。 
    
MAPI_W_POSITION_CHANGED 
  
> 调用成功，但  _bkOrigin_ 参数中指定的书签不再与上次使用时在同一行上设置。 如果尚未使用书签，则书签不再处于创建时的位置。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPITable：：SeekRow** 方法为游标BOOKMARK_CURRENT一个位置。 _lRowCount_ 参数指示光标移动的行数和移动方向。 
  
如果生成的位置超出表格的最后一行，光标将位于最后一行之后。 如果生成的位置在表格的第一行之前，光标将位于第一行的开头。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果  _bkOrigin_ 指向的行在表中不再存在，并且您无法为书签建立新位置，则返回MAPI_E_INVALID_BOOKMARK。 如果  _bkOrigin_ 指向的行不再存在，并且您可以为书签建立一个新位置，则返回MAPI_W_POSITION_CHANGED。 
  
指向折叠在表视图中的行的书签仍可以使用。 如果调用方尝试将光标移动到此类书签，将光标移到下一个可见行，并返回MAPI_W_POSITION_CHANGED。 
  
您可以在使用时或折叠行时移动折叠在视图外的位置的书签。 如果在折叠行时移动了书签，则保留书签中的一个位，以指示书签自上次使用以来是否移动过，或者，如果从未使用过，则自创建以来。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要指示 **SeekRow** 向后移动，在  _lRowCount_ 中传递负值。 若要搜索到表的开头，在  _lRowCount_ 中传递零，将值BOOKMARK_BEGINNING  _bkOrigin 中_。 
  
如果表中有很多行 **，SeekRow** 操作可能会很慢。 如果您需要在  _lplRowsS操作_ 参数的内容中返回行计数，则也会影响性能。 
  
 **SeekRow 返回 lRowCount** 指向的变量中实际搜索的行数（正数或  _负数_）。 在普通操作中，它应返回与 _lRowCount_ 传入的 _lplRowsS操作_ 相同的值，除非搜索到达表的开头或结尾。 
  
不要将  _lRowCount_ 设置为大于 50 的数。 若要查找更多行，请使用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 方法。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProcessor.cpp  <br/> |CMAPIProcessor：:P rocessMailboxTable  <br/> |MFCMAPI 使用 **IMAPITable：：SeekRow** 方法来在处理之前找到表的开头。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

