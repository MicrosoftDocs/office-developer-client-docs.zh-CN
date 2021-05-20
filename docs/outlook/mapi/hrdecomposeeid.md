---
title: HrDecomposeEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDecomposeEID
api_type:
- COM
ms.assetid: 4847838a-2ad8-4927-8f78-7fa5c8eb54eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d3ef8b61b6042d9c3e715168d9131a74facef000
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436109"
---
# <a name="hrdecomposeeid"></a>HrDecomposeEID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将对象（通常是邮件存储中的邮件）的复合条目标识符分隔到存储中的该对象的条目标识符和存储区的条目标识符中。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrDecomposeEID(
  LPMAPISESSION psession,
  ULONG cbEID,
  LPENTRYID pEID,
  ULONG FAR * pcbStoreEID,
  LPENTRYID FAR * ppStoreEID,
  ULONG FAR * pcbMsgEID,
  LPENTRYID FAR * ppMsgEID
);
```

## <a name="parameters"></a>参数

 _psession_
  
> [in]指向客户端应用程序使用的会话的指针。 
    
 _cbEID_
  
> [in]要分隔的复合条目标识符的大小（以字节为单位）。 
    
 _pEID_
  
> [in]指向要分隔的复合条目标识符的指针。 
    
 _分列存储 ID_
  
> [out]指向包含对象的邮件存储的条目标识符的返回大小（以字节为单位）的指针。 如果  _pEID_ 参数指向一个非编译项标识符，则这些  _pEID_ 参数指向一个零值。 
    
 _ppStoreEID_
  
> [out]指向指向包含对象的邮件存储的返回条目标识符的指针。 如果  _pEID_ 参数指向非编译项标识符，则  _ppStoreEID_ 参数中返回 NULL。 
    
 _atmMsgEID_
  
> [out]指向对象条目标识符的返回大小（以字节为单位）的指针。 如果  _pEID_ 参数指向一个非编译项标识符，则该  _pMsgEID_ 参数等于  _cbEID 参数_ 的值。 
    
 _ppMsgEID_
  
> [out]指向对象的返回条目标识符的指针的指针。 如果  _pEID_ 参数指向非编译项标识符，  _则 ppMsgEID_ 指向指向非编译项标识符副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果  _pEID_ 参数指定的标识符是复合标识符，则它将拆分为对象在其邮件存储中的条目标识符和存储的条目标识符。 仅复制未编译的条目标识符字符串。 要分隔的复合标识符通常由 [HrComposeEID](hrcomposeeid.md) 函数创建。 
  
## <a name="notes-to-callers"></a>给调用方的说明

保留  _pEID_ 参数的内存在成功完成此函数后释放。 调用实现负责为输出参数释放内存。 
  

