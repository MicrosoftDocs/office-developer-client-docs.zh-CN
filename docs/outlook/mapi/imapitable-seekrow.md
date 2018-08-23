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
ms.openlocfilehash: aead09eb10a3015a54867f14011c56b686bc8624
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586478"
---
# <a name="imapitableseekrow"></a>IMAPITable::SeekRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]书签标识的查找操作的起始位置。 可以使用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法中，创建一个书签，也可以传递预定义的以下值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表的开头开始查找操作。 
    
BOOKMARK_CURRENT 
  
> 启动搜索操作从光标所在的表中的一行。 
    
BOOKMARK_END 
  
> 从表末尾开始查找操作。 
    
 _lRowCount_
  
> [in]要移动的行数的签名的计数，从该书签开始_bkOrigin_参数标识。 
    
 _lplRowsSought_
  
> [输出]如果_lRowCount_上输入， _lplRowsSought_指向处理 seek 操作中的行数的有效指针，其中登录将向前或向后指示搜索的方向。 如果_lRowCount_为负数，则_lplRowsSought_为负数。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> Seek 操作已成功。
    
MAPI_E_BUSY 
  
> 正在进行中，可以防止起始行寻求操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_INVALID_BOOKMARK 
  
> _BkOrigin_参数中指定的书签无效，因为它已被删除或因为它超出请求的最后一行。 
    
MAPI_W_POSITION_CHANGED 
  
> 调用成功，但上次使用时不再在同一行设置_bkOrigin_参数中指定的书签。 如果未用过该书签，则不再在同一位置与创建它时一样。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPITable::SeekRow**方法建立新 BOOKMARK_CURRENT 位置的指针。 _LRowCount_参数指示光标移动的行和移动的方向的数量。 
  
如果最终位置超出最后一行的表，将光标定位的最后一行之后。 如果结果位置表的第一行之前，光标位于第一行的开头。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果所指的_bkOrigin_行不再存在表中，但无法建立的书签的新位置，则返回 MAPI_E_INVALID_BOOKMARK。 如果所指的_bkOrigin_行不再存在并且可以建立的书签的新位置，则返回 MAPI_W_POSITION_CHANGED。 
  
仍可用于指向折叠表视图的行的书签。 如果呼叫者尝试将光标移到此类书签，将光标移到下一个可见的行，并返回 MAPI_W_POSITION_CHANGED。 
  
您可以移动折叠视图，使用时，也可以在折叠行时的位置的书签。 如果折叠行次移动一个书签，有点保留指示书签具有其最后一次使用以来移动还是，如果它具有永远不会使用情况自其创建的书签。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要指示**SeekRow**向后移动，请在_lRowCount_传递负值。 若要搜索的表开头，传递零_lRowCount_和_bkOrigin_中的值 BOOKMARK_BEGINNING 中。 
  
如果有多个表中的行， **SeekRow**操作会很慢。 如果您需要在_lplRowsSought_参数的内容中返回的行数，还会影响性能。 
  
 **SeekRow**实际通过搜索、 正数或负数，变量所指的_lRowCount_中返回行的数。 在普通操作中，它应返回_lplRowsSought_相同的值为_lRowCount_，如除非搜索达到的开头或结尾的表。 
  
不要设置_lRowCount_为数大于 50。 若要 seek 通过更多的行，请使用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)方法。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProcessor.cpp  <br/> |CMAPIProcessor::ProcessMailboxTable  <br/> |MFCMAPI 使用**IMAPITable::SeekRow**方法查找表，然后处理的开头。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

