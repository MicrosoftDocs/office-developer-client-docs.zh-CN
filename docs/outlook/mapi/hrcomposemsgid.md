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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424061"
---
# <a name="hrcomposemsgid"></a>HrComposeMsgID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个 ASCII 字符串，该字符串代表对象（通常是邮件存储中的邮件）的复合条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
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
  
> [in]指向客户端应用程序使用的会话的指针。 
    
 _cbStoreRecordKey_
  
> [in]包含邮件或其他对象的邮件存储的记录键的大小（以字节为单位）。 如果在  _cbStoreRecordKey_ 参数中传递零，  _则 pszMsgID_ 参数指向转换为文本的条目标识符的副本。 
    
 _pStoreRecordKey_
  
> [in]指向包含邮件或其他对象的邮件存储的记录键的指针。 
    
 _cbMsgEID_
  
> [in]邮件或其他对象的条目标识符的大小（以字节为单位）。 
    
 _pMsgEID_
  
> [in]指向对象的条目标识符的指针。 
    
 _pszMsgID_
  
> [out]指向返回的 ASCII 字符串的指针。 如果  _cbStoreRecordKey_ 参数大于零，则  _pszMsgID_ 参数指向转换为文本的复合条目标识符。 如果  _cbStoreRecordKey_ 为零，  _则 pszMsgID_ 指向转换为文本的非编译项标识符。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果要创建复合条目标识符的邮件或其他对象驻留在邮件存储中，则从对象的条目标识符和存储的记录密钥创建标识符字符串。 如果对象不在存储区中，即，如果在  _cbStoreRecordKey_ 参数中传递的存储记录密钥的字节计数为零，则对象的条目标识符只是复制并转换为字符串。 
  
调用 **HrComposeMsgID** 函数等效于调用 [HrComposeEID](hrcomposeeid.md) 函数，然后调用 [HrSzFromEntryID](hrszfromentryid.md) 函数。 
  
 **HrComposeMsgID** 允许客户端应用程序通过复合条目标识符处理多个存储中的对象。 应用程序可以调用 [HrDecomposeMsgID](hrdecomposemsgid.md) 函数将复合条目标识符拆分为原始组成部分。 
  

