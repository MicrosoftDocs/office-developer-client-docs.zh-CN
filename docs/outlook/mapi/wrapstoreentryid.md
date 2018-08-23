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
ms.openlocfilehash: 45263396e69852a9ae17ff6fce284663bdf2fb07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585134"
---
# <a name="wrapstoreentryid"></a>WrapStoreEntryID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通过在邮件系统转换更易于使用的项标识符的消息存储内部的项标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]Flags 的位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串是 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _szDLLName_
  
> [in]消息存储提供程序 DLL 名称。 
    
 _cbOrigEntry_
  
> [in]大小，以字节为单位的消息存储的原始项标识符。 
    
 _lpOrigEntry_
  
> [in]指针指向包含原始的项标识符的[ENTRYID](entryid.md)结构。 
    
 _lpcbWrappedEntry_
  
> [输出]指向的大小，以字节为单位，新条目标识符的指针。 
    
 _lppWrappedEntry_
  
> [输出]为包含新的项标识符的**ENTRYID**结构指针的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

消息存储对象保留其只对与该消息存储的服务提供程序 coresident 有意义的内部条目标识符。 对于其他消息组件，MAPI 提供内部条目标识符，如属于消息存储使可识别的换行的版本。 Coresident 服务提供商应始终提供的原始解包的消息存储条目标识符;客户端应用程序应始终提供的换行的版本，然后可用任意位置和其他域中的消息的域。 
  
服务提供商可以换行使用**WrapStoreEntryID**函数或[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法，该调用**WrapStoreEntryID**函数方法的消息存储项标识符。 提供程序必须打包的项标识符时公开的消息存储**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或编写它到配置文件部分中，并公开**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 时属性。 MAPI 响应[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)呼叫时的换行消息存储项标识符。 
  
当客户端应用程序将传递给 MAPI 的换行的消息存储条目标识符时，例如进行[IMAPISession::OpenEntry](imapisession-openentry.md)通话，MAPI 进行解包的项标识符之前使用它来调用如[IMSProvider::Logon](imsprovider-logon.md)或[提供程序方法IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md)。 
  

