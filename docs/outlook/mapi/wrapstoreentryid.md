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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325667"
---
# <a name="wrapstoreentryid"></a>WrapStoreEntryID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件存储区的内部条目标识符转换为邮件系统更易于使用的条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _szDLLName_
  
> 实时邮件存储提供程序 DLL 的名称。 
    
 _cbOrigEntry_
  
> 实时邮件存储的原始条目标识符的大小 (以字节为单位)。 
    
 _lpOrigEntry_
  
> 实时指向包含原始条目标识符的[ENTRYID](entryid.md)结构的指针。 
    
 _lpcbWrappedEntry_
  
> 排除指向新条目标识符的大小 (以字节为单位) 的指针。 
    
 _lppWrappedEntry_
  
> 排除指向包含新条目标识符的**ENTRYID**结构的指针的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

邮件存储对象保留内部条目标识符, 该标识符仅对与该邮件存储 coresident 的服务提供程序有意义。 对于其他邮件组件, MAPI 提供了内部条目标识符的包装版本, 使其无法识别为邮件存储区。 应始终为 Coresident 服务提供程序提供原始的已解开邮件存储项标识符;应始终为客户端应用程序提供包装版本, 然后在邮件域和其他域中的任何位置使用该版本。 
  
服务提供程序可以使用**WrapStoreEntryID**函数或[IMAPISupport:: WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法包装邮件存储区条目标识符, 后者调用**WrapStoreEntryID**函数。 提供程序必须在公开邮件存储的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或将其写入配置文件部分时包装条目标识符, 并在公开**PR_STORE_ENTRYID**时 ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))财产. MAPI 对[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)调用进行响应时, 会对邮件存储条目标识符进行包装。 
  
当客户端应用程序将包装的邮件存储项标识符传递给 MAPI (例如在[IMAPISession:: OpenEntry](imapisession-openentry.md)调用中) 时, MAPI 将在使用它来调用提供程序方法 (如[IMSProvider:: Logon](imsprovider-logon.md) or [) 之前, 对条目标识符进行解包。IMSProvider:: CompareStoreIDs](imsprovider-comparestoreids.md)。 
  

