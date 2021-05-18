---
title: HrDecomposeMsgID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDecomposeMsgID
api_type:
- COM
ms.assetid: 5e6a9f3e-79be-4ffd-9d42-3a14cabb1435
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bff73ee5cf02680a2376106e21e0c743b995d336
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404433"
---
# <a name="hrdecomposemsgid"></a>HrDecomposeMsgID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将对象（通常是邮件存储中的邮件）复合条目标识符的 ASCII 表示形式分离到存储中的该对象的条目标识符和存储的条目标识符中。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrDecomposeMsgID(
  LPMAPISESSION psession,
  LPSTR szMsgID,
  ULONG FAR * pcbStoreEID,
  LPENTRYID FAR * ppStoreEID,
  ULONG FAR * pcbMsgEID,
  LPENTRYID FAR * ppMsgEID
);
```

## <a name="parameters"></a>参数

 _psession_
  
> [in]指向客户端应用程序使用的会话的指针。 
    
 _szMsgID_
  
> [in]表示对象的条目标识符的字符串。 
    
 _分列存储 ID_
  
> [out]指向包含对象的邮件存储的条目标识符的返回大小（以字节为单位）的指针。 如果  _szMsgID_ 参数指向一个非编译项标识符字符串，则  _该毫秒_ 存储 ID 参数将指向零。 
    
 _ppStoreEID_
  
> [out]指向指向包含对象的邮件存储的返回条目标识符的指针。 如果  _szMsgID_ 参数指向非编译项标识符，则  _ppStoreEID_ 参数中返回 NULL。 
    
 _atmMsgEID_
  
> [out]指向对象在其存储中的条目标识符的返回大小（以字节为单位）的指针。 如果  _szMsgID_ 参数指向一个非编译项标识符字符串，则  _这些参数等于_  _cbEID_ 参数的值。 
    
 _ppMsgEID_
  
> [out]指向指向对象在其存储中返回的条目标识符字符串的指针的指针。 如果  _szMsgID_ 参数指向非编译项标识符，  _则 ppMsgEID_ 指向指向非编译项标识符的转换副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果  _szMsgID_ 参数指定的标识符是复合标识符，它将从 ASCII 转换，并拆分为对象在其邮件存储中的条目标识符和存储区的条目标识符。 仅转换和复制未编译的条目标识符字符串。 要分隔的复合标识符字符串通常由 [HrComposeMsgID](hrcomposemsgid.md) 函数创建。 
  
调用 **HrDecomposeMsgID** 函数等效于调用 [HrEntryIDFromSz](hrentryidfromsz.md) 函数，然后 [调用 HrDecomposeEID](hrdecomposeeid.md) 函数。 
  

