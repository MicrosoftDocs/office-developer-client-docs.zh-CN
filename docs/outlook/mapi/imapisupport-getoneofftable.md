---
title: IMAPISupportGetOneOffTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetOneOffTable
api_type:
- COM
ms.assetid: 6800fd3a-aa43-45fe-9cc2-102d0ef43edf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 51cd838164e3de28ab33d6ab8a08a021360f3183
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775606"
---
# <a name="imapisupportgetoneofftable"></a>IMAPISupport::GetOneOffTable

  
  
**适用于**： Outlook 
  
返回到 MAPI 一次性表格 （所有通讯都簿提供程序支持创建新的收件人的模板的列表） 的指针。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，用于控制字符串列的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串列的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。
    
 _lppTable_
  
> [输出]指向一次性表格的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次性表。
    
## <a name="remarks"></a>说明

对于通讯簿提供程序支持对象实现**IMAPISupport::GetOneOffTable**方法。 通讯簿提供程序调用**GetOneOffTable**检索模板，用于创建新的收件人的完整列表。 此表包含会话中处于活动状态的通讯簿提供程序支持的模板，以及 MAPI 支持的模板。 
  
新创建的收件人可用于解决一条消息，也可以添加到通讯簿容器。
  
一次性表中所需的列组成的属性的列表，请参阅[一次性表](one-off-tables.md)。
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您已注册接收到此一次性表的更改的通知，您还将收到与其他提供程序的一次性表的更改的通知。 根据这些通知，您可以支持在当前会话过程中添加的新地址类型。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IMAPISupport::NewEntry](imapisupport-newentry.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[一次性表](one-off-tables.md)

