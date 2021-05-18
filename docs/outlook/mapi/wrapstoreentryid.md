---
title: WrapStoreEntryID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- WrapStoreEntryID
api_type:
- HeaderDef
ms.assetid: b20107e3-5e23-4cde-9cd6-670c914ea70a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e797a80cf8659baa7ca935f94b3ab65c200530a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409207"
---
# <a name="wrapstoreentryid"></a>WrapStoreEntryID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件存储的内部条目标识符转换为邮件系统更可用条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
WrapStoreEntryID(
  ULONG ulFlags,
  LPSTR szDLLName,
  ULONG cbOrigEntry,
  LPENTRYID lpOrigEntry,
  ULONG * lpcbWrappedEntry,
  LPENTRYID * lppWrappedEntry
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _szDLLName_
  
> [in]邮件存储提供程序 DLL 的名称。 
    
 _cbOrigEntry_
  
> [in]邮件存储的原始条目标识符的大小（以字节为单位）。 
    
 _lpOrigEntry_
  
> [in]指向包含原始条目标识符的 [ENTRYID](entryid.md) 结构的指针。 
    
 _lpcbWrappedEntry_
  
> [out]指向新条目标识符的大小（以字节为单位）的指针。 
    
 _lppWrappedEntry_
  
> [out]指向包含新条目标识符 **的 ENTRYID** 结构的指针的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

邮件存储对象保留一个内部条目标识符，该标识符仅对具有该邮件存储的服务提供商核心标识有意义。 对于其他邮件组件，MAPI 提供内部条目标识符的包装版本，使其可识别为属于邮件存储的版本。 应始终为 Coresident 服务提供商提供原始未包的邮件存储条目标识符;应始终为客户端应用程序提供包装版本，该版本随后将在邮件域和其他域中的任何位置使用。 
  
服务提供商可以使用 **WrapStoreEntryID** 函数或调用 **WrapStoreEntryID** 函数的 [IMAPISupport：：WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法包装邮件存储条目标识符。 当公开邮件存储的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或将其写入配置文件部分，以及公开 **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性时，提供程序必须包装条目标识符。 MAPI 在响应 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 调用时封装邮件存储条目标识符。 
  
当客户端应用程序将包装的邮件存储条目标识符传递给 MAPI（例如 [，在 IMAPISession：：OpenEntry](imapisession-openentry.md) 调用中）时，MAPI 在使用它调用提供程序方法（如 [IMSProvider：：Logon](imsprovider-logon.md) 或 [IMSProvider：：CompareStoreIDs）之前将](imsprovider-comparestoreids.md)取消封装条目标识符。 
  

