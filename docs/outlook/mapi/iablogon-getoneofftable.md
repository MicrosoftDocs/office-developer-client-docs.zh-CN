---
title: IABLogonGetOneOffTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.GetOneOffTable
api_type:
- COM
ms.assetid: 7ac2a8d4-6890-4346-a6b6-34deca9dab50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 326a78ed512ec82a9f16b1540aad60954ab2d864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411874"
---
# <a name="iablogongetoneofftable"></a>IABLogon::GetOneOffTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个一次性模板表, 用于创建要添加到传出邮件的收件人列表中的收件人。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制包含在表中的字符串列的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。
    
 _lppTable_
  
> 排除指向一次性表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次性表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且通讯簿提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 并且通讯簿提供程序仅支持 unicode。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不提供任何一次性模板。
    
## <a name="remarks"></a>说明

MAPI 调用**GetOneOffTable**方法来创建可用的一次性模板, 以创建收件人。 新收件人将添加到传出邮件的收件人列表中。 通讯簿提供程序应支持对其一次性表发出通知, 以通知 MAPI 的模板修改。 MAPI 保持打开一个 "一次性" 表以启用动态更新。 
  
通讯簿提供程序还可以支持其每个容器的一次性表。 调用方通过调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来检索此一次性表。 可通过此表使用的模板将收件人添加到容器中。 有关这两种类型的一次性表之间的区别的讨论, 请参阅[实现一次性表](implementing-one-off-tables.md)。
  
若要获取通讯簿提供程序的一次性表格中所需列的列表, 请参阅[一次性表格](one-off-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IAddrBook::NewEntry](iaddrbook-newentry.md)
  
[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

