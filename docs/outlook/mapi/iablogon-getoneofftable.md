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
  
返回用于创建要添加到传出邮件的收件人列表的收件人的一次模板表。
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制表中包含的字符串列类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。
    
 _lppTable_
  
> [out]指向指向一次表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索一次表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，通讯簿提供程序不支持 Unicode，或者MAPI_UNICODE设置该地址簿提供程序仅支持 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不提供任何一次使用模板。
    
## <a name="remarks"></a>备注

MAPI 调用 **GetOneOffTable** 方法，使一次可用模板可用于创建收件人。 新收件人将添加到传出邮件的收件人列表中。 通讯簿提供程序应支持在一对一表上发送通知，以通知 MAPI 模板修改。 MAPI 使一次表保持打开状态，以启用动态更新。 
  
通讯簿提供程序还可以支持每个容器的一对一表。 调用方通过调用容器的[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法并请求 PR_CREATE_TEMPLATES ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 检索此一) 表。  通过此表提供的模板用于将收件人添加到容器。 有关这两种类型的一键式表之间的差异的讨论，请参阅 [Implementing One-Off Tables](implementing-one-off-tables.md)。
  
有关通讯簿提供程序的一键式表中的所需列的列表，请参阅 [一键式表](one-off-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IAddrBook::NewEntry](iaddrbook-newentry.md)
  
[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

