---
title: IMAPITableFindRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.FindRow
api_type:
- COM
ms.assetid: 6511368c-9777-497e-9eea-cf390c04b92e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a5364af229721d101f38d2f054f528169b48c09e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429570"
---
# <a name="imapitablefindrow"></a>IMAPITable::FindRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查找表中与特定搜索条件匹配的下一行，并移动光标到该行。
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]指向描述 [搜索条件的 SRestriction](srestriction.md) 结构的指针。 
    
 _BkOrigin_
  
> [in]一个书签，用于标识 **FindRow 应** 开始搜索的行。 可以使用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md) 方法创建书签，也可以传递以下预定义值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表开头搜索。 
    
BOOKMARK_CURRENT 
  
> 从光标所在的表格中的行进行搜索。 
    
BOOKMARK_END 
  
> 从表末尾搜索。 
    
 _ulFlags_
  
> [in]控制搜索方向的标志的位掩码。 可以设置以下标志：
    
DIR_BACKWARD 
  
> 从书签标识的行向后搜索。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 查找操作成功。
    
MAPI_E_INVALID_BOOKMARK 
  
> _BkOrigin_ 参数中的书签无效，因为它已被删除或超出请求的最后一行。 
    
MAPI_E_NOT_FOUND 
  
> 未找到与限制匹配的行。
    
MAPI_W_POSITION_CHANGED
  
> 调用成功，但操作中使用的书签不再与上次使用时在同一行上设置;如果尚未使用书签，则它不再处于创建时的位置。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 请参阅 [使用宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPITable：：FindRow** 方法查找表格中的第一行，以匹配 _lpRestriction_ 参数指向的 **SRestriction** 结构中描述的一组搜索条件。 
  
通常 **，FindRow** 从指定书签向前搜索。 调用方可以通过在  _ulFlags_ 参数中设置 DIR_BACKWARD 标志，将搜索设置为从书签向后移动。 从当前书签开始向前搜索;从书签之前的行开始向后搜索。 搜索的结束位置正好在找到满足限制的第一行之前。 
  
如果  _BkOrigin_ 参数中的书签指向的行不再存在于表中，并且表无法为书签建立新位置 **，FindRow** 将返回MAPI_E_INVALID_BOOKMARK。 如果  _BkOrigin_ 指向的行不再存在，并且表能够为书签建立一个新位置 **，FindRow** 将返回MAPI_W_POSITION_CHANGED。 
  
如果在  _BkOrigin_ 中传递的书签BOOKMARK_BEGINNING或BOOKMARK_END， **则 FindRow** MAPI_E_NOT_FOUND如果未找到匹配的行。 如果  _BkOrigin_ 中使用的书签 **BOOKMARK_CURRENT，FindRow** 可以返回 MAPI_W_POSITION_CHANGED，MAPI_E_INVALID_BOOKMARK，因为始终存在当前光标位置。 
  
所有 **表** 都需要 PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性列， **并且 FindRow** 的所有实现都需要支持基于 PR_INSTANCE_KEY 查找行的调用。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

只有当搜索遵循与表组织相同的方向时 **，FindRow** 执行的前缀搜索类型才有用。 为了实现所需的行为，属性限制结构中传递的 RELOP_GE 隐含的比较函数应该与表排序顺序所基于的比较函数相同。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可以使用 **FindRow** 支持基于用户输入的字符串进行滚动，尤其是在地址对话框的列表框中。 在此类型的滚动中，用户输入所需字符串值的逐步长前缀，你可以定期发出 **FindRow** 调用以跳转到与前缀匹配的第一行。 光标跳转的方向取决于搜索设置运行的方向。 
  
若要使用 **FindRow，** 必须设置书签。 字符串搜索可以源自任何书签，包括来自指示当前位置以及表格开头和结尾的预设书签。 如果表中有很多行，则搜索操作可能会很慢。
  
使用限制查找字符串前缀进行滚动，如下所示。 For forward searching on a column sorted in ascending order and for backward searching on a column sorted in descending order， pass a property restriction structure in the  _lpRestriction_ parameter with the relation **RELOP_GE** and the appropriate property tag and prefix， using the format  _tag_ **GE** _prefix_. 
  
有关使用限制结构指定筛选器的信息，请参阅关于 [限制](about-restrictions.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用 **IMAPITable：：FindRow** 方法来查找与限制匹配的行。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[SRestriction](srestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

