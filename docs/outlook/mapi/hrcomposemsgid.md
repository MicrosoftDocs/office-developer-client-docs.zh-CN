---
title: HrComposeMsgID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrComposeMsgID
api_type:
- COM
ms.assetid: bb76b147-6552-4cc4-920f-699170aea17f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c035780d3d790d94551860a418401e63da1c2151
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348046"
---
# <a name="hrcomposemsgid"></a>HrComposeMsgID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个 ASCII 字符串, 该字符串表示对象的复合条目标识符, 通常是邮件存储区中的邮件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrComposeMsgID(
  LPMAPISESSION psession,
  ULONG cbStoreRecordKey,
  LPBYTE pStoreRecordKey,
  ULONG cbMsgEID,
  LPENTRYID pMsgEID,
  LPSTR FAR * pszMsgID
);
```

## <a name="parameters"></a>参数

 _psession_
  
> 实时指向客户端应用程序正在使用的会话的指针。 
    
 _cbStoreRecordKey_
  
> 实时包含邮件或其他对象的邮件存储区的记录键的大小 (以字节为单位)。 如果在_cbStoreRecordKey_参数中传递零, 则_pszMsgID_参数指向已转换为 text 的条目标识符的副本。 
    
 _pStoreRecordKey_
  
> 实时指向邮件存储区中包含邮件或其他对象的记录键的指针。 
    
 _cbMsgEID_
  
> 实时邮件或其他对象的条目标识符的大小 (以字节为单位)。 
    
 _pMsgEID_
  
> 实时指向对象的条目标识符的指针。 
    
 _pszMsgID_
  
> 排除指向返回的 ASCII 字符串的指针。 如果_cbStoreRecordKey_参数大于零, 则_pszMsgID_参数指向转换为 text 的复合条目标识符。 如果_cbStoreRecordKey_为零, 则_pszMsgID_指向已转换为 text 的 noncompound 条目标识符。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果要为其创建复合条目标识符的邮件或其他对象驻留在邮件存储区中, 则将从该对象的条目标识符和存储的记录密钥创建标识符字符串。 如果对象不在 store 中 (即, 如果在_cbStoreRecordKey_参数中传递的 store 记录关键字的字节数为零), 则只会复制对象的条目标识符, 并将其转换为字符串。 
  
调用**HrComposeMsgID**函数等效于调用[HrComposeEID](hrcomposeeid.md)函数, 然后调用[HrSzFromEntryID](hrszfromentryid.md)函数。 
  
 **HrComposeMsgID**使客户端应用程序能够通过使用复合条目标识符来处理多个存储中的对象。 应用程序可以调用[HrDecomposeMsgID](hrdecomposemsgid.md)函数, 以将复合条目标识符拆分为其原始要素。 
  

