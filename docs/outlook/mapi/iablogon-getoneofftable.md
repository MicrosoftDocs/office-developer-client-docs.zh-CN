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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b8a6d74df3749a5445d95ad392f7f88d27190bfc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775214"
---
# <a name="iablogongetoneofftable"></a>IABLogon::GetOneOffTable

  
  
**适用于**： Outlook 
  
返回一个一次性模板，用于创建要添加到的传出邮件的收件人列表的收件人的表。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，用于控制字符串表中包含的列的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串列的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。
    
 _lppTable_
  
> [输出]指向一次性表格的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次性表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志通讯簿提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和通讯簿提供程序支持仅 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不提供任何一次性模板。
    
## <a name="remarks"></a>说明

MAPI 调用**GetOneOffTable**方法使可用一次性模板创建收件人。 新的收件人添加到的传出邮件的收件人列表。 通讯簿提供程序应支持通知模板修改的 MAPI 其一次性表上的通知。 MAPI 保持打开，以允许动态更新一次性表。 
  
通讯簿提供程序还可以为每个其容器支持一次性表。 呼叫者通过调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来检索此一次性表。 可通过此表的模板用于将收件人添加到容器。 有关两种类型的一次性表之间的差异的讨论，请参阅[实现一次性表](implementing-one-off-tables.md)。
  
通讯簿提供程序的一次性表中所需的列的列表，请参阅[一次性表](one-off-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IAddrBook::NewEntry](iaddrbook-newentry.md)
  
[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

