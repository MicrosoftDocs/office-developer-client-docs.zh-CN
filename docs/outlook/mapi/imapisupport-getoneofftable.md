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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c0beec8a0b234794d3f623c4ceac773db698dd79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412756"
---
# <a name="imapisupportgetoneofftable"></a>IMAPISupport::GetOneOffTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指向 MAPI 一次性表 (所有通讯簿提供程序为创建新收件人所支持的模板列表) 的指针。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制字符串列的类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。
    
 _lppTable_
  
> 排除指向一次性表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次性表。
    
## <a name="remarks"></a>说明

为通讯簿提供程序支持对象实现了**IMAPISupport:: GetOneOffTable**方法。 通讯簿提供程序调用**GetOneOffTable**以检索用于创建新收件人的模板的完整列表。 此表包含了通讯簿提供程序在会话支持中处于活动状态的模板以及 MAPI 支持的模板。 
  
可以使用新创建的收件人来处理邮件, 也可以将其添加到通讯簿容器中。
  
有关构成一次性表中设置的必需列的属性列表, 请参阅[一次性表](one-off-tables.md)。
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您已注册接收对此一次性表所做更改的通知, 则还将接收对其他提供程序的一次性表所做更改的通知。 根据这些通知, 可以支持在当前会话期间添加的新地址类型。
  
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

