---
title: IMAPISupportWrapStoreEntryID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.WrapStoreEntryID
api_type:
- COM
ms.assetid: 923fb879-5f32-4fe2-8920-2ec17002256c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a623ef24f76dae93bfc13e6613e885a120f3278e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341284"
---
# <a name="imapisupportwrapstoreentryid"></a>IMAPISupport::WrapStoreEntryID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件存储区的内部条目标识符转换为 MAPI 标准格式的条目标识符。
  
```cpp
HRESULT WrapStoreEntryID(
ULONG cbOrigEntry,
LPENTRYID lpOrigEntry,
ULONG FAR * lpcbWrappedEntry,
LPENTRYID FAR * lppWrappedEntry
);
```

## <a name="parameters"></a>参数

 _cbOrigEntry_
  
> 实时条目标识符中由_lpOrigEntry_参数指向的字节数。 
    
 _lpOrigEntry_
  
> 实时指向邮件存储区的专用条目标识符的指针。
    
 _lpcbWrappedEntry_
  
> 排除指向条目标识符中由_lppWrappedEntry_参数指向的字节计数的指针。 
    
 _lppWrappedEntry_
  
> 排除指向指向已包装条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功包装条目标识符。
    
## <a name="remarks"></a>注解

**IMAPISupport:: WrapStoreEntryID**方法是为所有服务提供程序支持对象实现的。 服务提供程序使用**WrapStoreEntryID**让 MAPI 为封装了存储区内部项标识符的邮件存储区生成条目标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当客户端调用您的邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性, 并且您的邮件存储区使用专用格式的条目标识符时, 请调用**WrapStoreEntryID**并返回_lppWrappedEntry_参数指向的条目标识符。 
  
对[IMSProvider:: Logon](imsprovider-logon.md)和[IMSLogon:: CompareEntryIDs](imslogon-compareentryids.md)方法的调用始终获取存储区的专用条目标识符;包装的版本仅在客户端应用程序和 MAPI 之间使用。 
  
使用完条目标识符后, 使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放_lppWrappedEntry_参数指向的条目标识符所对应的内存。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)
  
[IMSLogon::CompareEntryIDs](imslogon-compareentryids.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

