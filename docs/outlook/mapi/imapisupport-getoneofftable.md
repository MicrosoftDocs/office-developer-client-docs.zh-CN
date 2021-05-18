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
  
返回一个指向 MAPI 一 (表的指针，该表包含所有通讯簿提供程序都支持创建新收件人的) 。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制字符串列类型的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。
    
 _lppTable_
  
> [out]指向指向一次表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次表。
    
## <a name="remarks"></a>备注

**为通讯簿提供程序支持对象实现 IMAPISupport：：GetOneOffTable** 方法。 通讯簿提供程序调用 **GetOneOffTable** 以检索用于创建新收件人的模板的完整列表。 此表包括通讯簿提供程序在会话支持中处于活动状态的模板，以及 MAPI 支持的模板。 
  
新创建的收件人可用于处理邮件，也可以添加到通讯簿容器。
  
有关一对一表中必需列集的属性列表，请参阅 [一键式表格](one-off-tables.md)。
  
在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。 此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果注册为接收对此一键式表的更改的通知，还将收到其他提供商的一键式表更改通知。 根据这些通知，可以支持在当前会话期间添加的新地址类型。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IMAPISupport::NewEntry](imapisupport-newentry.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[一键式表](one-off-tables.md)

