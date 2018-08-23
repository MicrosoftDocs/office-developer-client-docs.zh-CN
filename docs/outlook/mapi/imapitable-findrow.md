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
ms.openlocfilehash: 2a50a5f536e337e5ca37e61f17d4dfd40aa9c51e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565331"
---
# <a name="imapitablefindrow"></a>IMAPITable::FindRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在与特定的搜索条件匹配并将光标移至该行的表中查找的下一行。
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]指向介绍搜索条件的[SRestriction](srestriction.md)结构的指针。 
    
 _BkOrigin_
  
> [in]标识**FindRow**开始搜索的位置行的书签。 可以使用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法中，创建一个书签，也可以传递预定义的以下值之一。 
    
BOOKMARK_BEGINNING 
  
> 从表开始搜索。 
    
BOOKMARK_CURRENT 
  
> 从光标位于何处表中的行进行搜索。 
    
BOOKMARK_END 
  
> 从表末尾的搜索。 
    
 _ulFlags_
  
> [in]位掩码的标志，用于控制搜索的方向。 可以设置以下标记：
    
DIR_BACKWARD 
  
> 向后搜索从书签标识的一行。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 查找操作成功。
    
MAPI_E_INVALID_BOOKMARK 
  
> _BkOrigin_参数中的书签无效，因为它已被删除或因为它超出请求的最后一行。 
    
MAPI_E_NOT_FOUND 
  
> 符合限制不找到任何行。
    
MAPI_W_POSITION_CHANGED
  
> 调用成功，但操作中使用的书签不再设置在所在的行时上次使用它;如果未用过该书签，，则不再中位置相同时创建它。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPITable::FindRow**方法在要与一组_lpRestriction_参数指向的**SRestriction**结构中所述的搜索条件匹配的表中查找第一行。 
  
通常， **FindRow**向前搜索从指定的书签。 呼叫者可以设置搜索从向后移动书签通过_ulFlags_参数中设置 DIR_BACKWARD 标志。 从当前书签; 向前搜索开始向后搜索启动之前书签行中。 第一行找到的满足限制之前，搜索的结束位置。 
  
如果所指的_BkOrigin_参数中的书签的行不再存在于表以及表无法建立的书签的新位置**FindRow**返回 MAPI_E_INVALID_BOOKMARK。 如果所指的_BkOrigin_行不再存在并且表是能够建立的书签的新位置， **FindRow**返回 MAPI_W_POSITION_CHANGED。 
  
如果_BkOrigin_中传递的书签，BOOKMARK_BEGINNING 或 BOOKMARK_END **FindRow**返回 MAPI_E_NOT_FOUND，如果未不找到任何匹配的行。 如果_BkOrigin_中使用的书签，BOOKMARK_CURRENT **FindRow**可以返回 MAPI_W_POSITION_CHANGED 但不是 MAPI_E_INVALID_BOOKMARK，因为始终没有当前光标位置。 
  
**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性栏是必需的所有表，并支持呼叫寻求基于 PR_INSTANCE_KEY 行所需的所有**FindRow**实现。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

仅在搜索将遵循相同的方向表组织时有用的前缀搜索由**FindRow**执行的类型。 为了实现所需的行为，比较函数暗示**RELOP_GE**传递在属性限制结构应为相同的比较功能所基于的表排序次序。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**FindRow**支持滚动基于用户，特别是在地址对话框内的列表框中键入的字符串。 在此类型的滚动，用户输入的一个所需的字符串值，会越来越长前缀和定期可以发出**FindRow**呼叫跳转到前缀匹配的第一行。 光标跳转的方向取决于哪个方向搜索设置为运行。 
  
若要使用**FindRow**，必须设置书签。 字符串搜索可以源自任何书签，包括预设书签指示当前位置的开头和末尾表。 如果有大量的表中的行，则搜索操作会很慢。
  
使用限制查找字符串前缀滚动，如下所示。 对于按升序排序的列上向前搜索和按降序排序的列上向后搜索，传递的关系**RELOP_GE** _lpRestriction_参数和相应的属性限制结构属性标记和前缀，使用格式_标记_ **GE** _前缀_。 
  
有关使用限制结构指定筛选器的详细信息，请参阅[有关限制](about-restrictions.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用**IMAPITable::FindRow**方法查找与限制匹配的行。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[SRestriction](srestriction.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

