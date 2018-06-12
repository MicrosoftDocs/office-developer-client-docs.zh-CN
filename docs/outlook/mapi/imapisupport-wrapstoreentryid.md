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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 25c04f8dee012f4985db98df7d1b3ae5536ef6b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775671"
---
# <a name="imapisupportwrapstoreentryid"></a>IMAPISupport::WrapStoreEntryID

  
  
**适用于**： Outlook 
  
转换 MAPI 标准格式中的项标识符的消息存储内部的项标识符。
  
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
  
> [in]在_lpOrigEntry_参数指向的项标识符的字节数。 
    
 _lpOrigEntry_
  
> [in]指向消息存储库的专用的项标识符的指针。
    
 _lpcbWrappedEntry_
  
> [输出]一个指向_lppWrappedEntry_参数指向该条目标识符中的字节数。 
    
 _lppWrappedEntry_
  
> [输出]指向与换行的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功自动换行的项标识符。
    
## <a name="remarks"></a>备注

**IMAPISupport::WrapStoreEntryID**方法将执行所有服务提供商支持对象。 服务提供商使用**WrapStoreEntryID**已生成的存储内部的项标识符的换行的消息存储的项标识符的 MAPI。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当客户端调用消息存储库[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性，您和您的消息存储区专用格式中使用的项标识符，调用**WrapStoreEntryID**并返回_lppWrappedEntry_参数指向的项标识符。 
  
对[IMSProvider::Logon](imsprovider-logon.md)和[IMSLogon::CompareEntryIDs](imslogon-compareentryids.md)方法的调用始终获取存储区的专用条目标识符;客户端应用程序和 MAPI 之间只使用换行的版本。 
  
忙时使用的项标识符完使用[MAPIFreeBuffer](mapifreebuffer.md)函数_lppWrappedEntry_参数指向的项标识符的内存。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)
  
[IMSLogon::CompareEntryIDs](imslogon-compareentryids.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

