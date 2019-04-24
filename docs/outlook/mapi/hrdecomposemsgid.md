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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348088"
---
# <a name="hrdecomposemsgid"></a>HrDecomposeMsgID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将对象的复合条目标识符 (通常是邮件存储区中的邮件) 的 ASCII 表示形式分离到存储区中该对象的条目标识符和存储的条目标识符中。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
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
  
> 实时指向客户端应用程序正在使用的会话的指针。 
    
 _szMsgID_
  
> 实时表示对象的条目标识符的字符串。 
    
 _pcbStoreEID_
  
> 排除指向包含该对象的邮件存储区的条目标识符的返回大小 (以字节为单位)。 如果_szMsgID_参数指向 noncompound 条目标识符字符串, 则_pcbStoreEID_参数将指向零。 
    
 _ppStoreEID_
  
> 排除指向指向包含该对象的邮件存储区的返回项标识符的指针的指针。 如果_szMsgID_参数指向 noncompound 条目标识符, 则在_ppStoreEID_参数中返回 NULL。 
    
 _pcbMsgEID_
  
> 排除指向其存储中的对象的条目标识符的返回大小 (以字节为单位) 的指针。 如果_szMsgID_参数指向 noncompound 条目标识符字符串, 则_pcbMsgEID_参数等于_cbEID_参数的值。 
    
 _ppMsgEID_
  
> 排除指向指向其存储中的对象的返回项标识符字符串的指针的指针。 如果_szMsgID_参数指向 noncompound 条目标识符, 则_ppMsgEID_指向指向 noncompound 条目标识符的转换副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果_szMsgID_参数指定的标识符是复合标识符, 则将其从 ASCII 转换为, 并拆分为其邮件存储区中的对象的条目标识符和存储的条目标识符。 Noncompound 条目标识符字符串是简单转换和复制的。 要分隔的复合标识符字符串通常是由[HrComposeMsgID](hrcomposemsgid.md)函数创建一个。 
  
调用**HrDecomposeMsgID**函数等效于调用[HrEntryIDFromSz](hrentryidfromsz.md)函数, 然后调用[HrDecomposeEID](hrdecomposeeid.md)函数。 
  

