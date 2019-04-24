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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329076"
---
# <a name="imapitablefindrow"></a>IMAPITable::FindRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在表中查找与特定搜索条件匹配的下一行, 并将光标移至该行。
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> 实时指向描述搜索条件的[SRestriction](srestriction.md)结构的指针。 
    
 _BkOrigin_
  
> 实时一个书签, 用于标识**FindRow**应开始搜索的行。 可以使用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)方法创建书签, 或者可以传递下列预定义值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表的开头进行搜索。 
    
BOOKMARK_CURRENT 
  
> 从游标所在的表中的行进行搜索。 
    
BOOKMARK_END 
  
> 从表的末尾开始搜索。 
    
 _ulFlags_
  
> 实时用于控制搜索方向的标志的位掩码。 可以设置以下标志:
    
DIR_BACKWARD 
  
> 从书签标识的行向后搜索。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 查找操作成功。
    
MAPI_E_INVALID_BOOKMARK 
  
> _BkOrigin_参数中的书签无效, 因为它已被删除或超出了最后请求的行。 
    
MAPI_E_NOT_FOUND 
  
> 找不到与限制匹配的行。
    
MAPI_W_POSITION_CHANGED
  
> 调用成功, 但在操作中使用的书签不再设置为与上次使用时相同的行;如果书签尚未使用, 它将不再位于创建时的位置。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPITable:: FindRow**方法定位表中的第一行, 以匹配_lpRestriction_参数指向的**SRestriction**结构中所述的一组搜索条件。 
  
通常情况下, **FindRow**从指定书签向前搜索。 调用方可以通过在_ulFlags_参数中设置 DIR_BACKWARD 标志, 将搜索设置为在书签中向后移动。 向前搜索从当前书签开始;向后搜索将从书签之前的行开始。 搜索的结束位置恰好在找到满足限制的第一行之前。 
  
如果_BkOrigin_参数中的书签所指向的行在表中不再存在, 并且该表无法为该书签建立新的位置, 则**FindRow**将返回 MAPI_E_INVALID_BOOKMARK。 如果_BkOrigin_所指向的行不再存在, 并且表格能够为该书签建立一个新位置, 则**FindRow**将返回 MAPI_W_POSITION_CHANGED。 
  
如果_BkOrigin_中传递的书签是 BOOKMARK_BEGINNING 或 BOOKMARK_END, 如果找不到匹配的行, **FindRow**将返回 MAPI_E_NOT_FOUND。 如果_BkOrigin_中使用的书签为 BOOKMARK_CURRENT, 则**FindRow**可以返回 MAPI_W_POSITION_CHANGED 而不是 MAPI_E_INVALID_BOOKMARK, 因为始终存在当前游标位置。 
  
所有表都需要**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性列, **FindRow**的所有实现都必须支持查找基于 PR_INSTANCE_KEY 的行的调用。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**FindRow**执行的前缀搜索的类型仅在搜索与表组织的方向相同时才有用。 为了实现所需的行为, 在属性限制结构中传递的**RELOP_GE**暗示的比较函数应与表排序顺序所基于的比较函数相同。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**FindRow**支持基于用户键入的字符串滚动, 尤其是在地址对话框内的列表框中。 在这种类型的滚动中, 用户可以输入所需字符串值的渐进更长的前缀, 并且可以定期发出**FindRow**调用以跳转到与前缀匹配的第一行。 光标跳转的方向取决于搜索设置的运行方向。 
  
若要使用**FindRow**, 必须设置书签。 字符串搜索可以来自任何书签, 包括从表示当前位置的预设书签到表格的开始和结束。 如果表中有大量的行, 则搜索操作可能会很慢。
  
使用限制来查找用于滚动的字符串前缀, 如下所示。 对于按升序排序的列和对按降序排序的列进行的向前搜索, 请在_lpRestriction_参数中使用关系**RELOP_GE**传递属性限制结构, 并使用适当的使用格式_标记_ **GE** _前缀_的属性标记和前缀。 
  
有关使用限制结构指定筛选器的详细信息, 请参阅[关于限制](about-restrictions.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用**IMAPITable:: FindRow**方法查找匹配限制的行。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[SRestriction](srestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

