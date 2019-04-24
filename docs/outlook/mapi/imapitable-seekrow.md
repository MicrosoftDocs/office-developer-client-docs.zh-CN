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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328824"
---
# <a name="imapitableseekrow"></a>IMAPITable::SeekRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将光标移到表中的特定位置。
  
```cpp
HRESULT SeekRow(
BOOKMARK bkOrigin,
LONG lRowCount,
LONG FAR * lplRowsSought
);
```

## <a name="parameters"></a>参数

 _bkOrigin_
  
> 实时用于标识查找操作的起始位置的书签。 可以使用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)方法创建书签, 或者可以传递下列预定义值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表的开头开始查找操作。 
    
BOOKMARK_CURRENT 
  
> 从游标所在的表的行中启动 seek 操作。 
    
BOOKMARK_END 
  
> 从表的末尾开始查找操作。 
    
 _lRowCount_
  
> 实时从_bkOrigin_参数标识的书签开始要移动的行数的已签名计数。 
    
 _lplRowsSought_
  
> 排除如果_lRowCount_是输入上的有效指针, 则_lplRowsSought_指向在 seek 操作中处理的行数、指示搜索方向的符号 (向前或向后)。 如果_lRowCount_为负, 则_lplRowsSought_为负。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> seek 操作成功完成。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止启动行查找操作。 应允许正在进行的操作完成, 或者应已停止。
    
MAPI_E_INVALID_BOOKMARK 
  
> 在_bkOrigin_参数中指定的书签无效, 因为它已被删除或超出了最后请求的行。 
    
MAPI_W_POSITION_CHANGED 
  
> 调用成功, 但在_bkOrigin_参数中指定的书签不再设置为与上次使用时相同的行。 如果尚未使用该书签, 它将不再位于创建时的位置。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPITable:: SeekRow**方法为游标建立了一个新的 BOOKMARK_CURRENT 位置。 _lRowCount_参数指示光标移动的行数和移动方向。 
  
如果生成的位置超出了表的最后一行, 则将光标定位在最后一行之后。 如果生成的位置在表的第一行之前, 则光标定位在第一行的开头。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果_bkOrigin_中不再存在指向的行, 并且无法为该书签建立新的位置, 请返回 MAPI_E_INVALID_BOOKMARK。 如果_bkOrigin_所指向的行不再存在, 并且您可以为该书签建立一个新位置, 请返回 MAPI_W_POSITION_CHANGED。 
  
仍然可以使用指向折叠在表视图之外的行的书签。 如果调用方尝试将光标移动到此类书签, 请将光标移到下一个可见的行, 并返回 MAPI_W_POSITION_CHANGED。 
  
您可以在使用时或在行折叠时, 将位置的书签移动到视图之外。 如果在折叠行时移动书签, 则在书签中保留一位, 以指示该书签自上次使用后是否已移动, 或者, 自创建以来, 如果从未使用过该书签。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要指示**SeekRow**的后向移动, 请在_lRowCount_中传递一个负值。 若要搜索到表的开头, 请在_lRowCount_中传递零, 并在_bkOrigin_中传递值 BOOKMARK_BEGINNING。 
  
如果表中有很多行, 则**SeekRow**操作可能会很慢。 如果您需要在_lplRowsSought_参数的内容中返回行数, 也会影响性能。 
  
 **SeekRow**返回在_lRowCount_指向的变量中实际搜索的行数 (正数或负数)。 在普通操作中, 它应为在_lRowCount_中传递的_lplRowsSought_返回相同的值, 除非搜索到达表的开头或结尾。 
  
请勿将_lRowCount_设置为大于50的数字。 若要查找更多的行, 请使用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)方法。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProcessor  <br/> |CMAPIProcessor::P rocessmailboxtable  <br/> |MFCMAPI 使用**IMAPITable:: SeekRow**方法在处理前查找表的开头。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

