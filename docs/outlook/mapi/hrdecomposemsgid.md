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
ms.openlocfilehash: 828d7ebcbceead02441165e3af92ec7b47d9f001
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564624"
---
# <a name="hrdecomposemsgid"></a>HrDecomposeMsgID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
用于分隔 ASCII 标识符的表示形式复合条目的对象，通常一条消息的消息存储，该对象存储区中的项标识符和存储的项标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]加入会话，使用客户端应用程序的指针。 
    
 _szMsgID_
  
> [in]表示对象的项标识符的字符串。 
    
 _pcbStoreEID_
  
> [输出]指向返回的大小，以字节为单位的项标识符的消息存储库包含对象的指针。 如果_szMsgID_参数指向的非复合条目标识符字符串，然后为零的_pcbStoreEID_参数点。 
    
 _ppStoreEID_
  
> [输出]为返回的项标识符的消息存储库包含对象的指针的指针。 如果_szMsgID_参数指向的非复合条目标识符，则_ppStoreEID_参数中返回 NULL。 
    
 _pcbMsgEID_
  
> [输出]对返回的大小，以字节为单位，该对象在其存储区中的项标识符的指针。 如果_szMsgID_参数指向非复合条目标识符字符串， _pcbMsgEID_参数等于_cbEID_参数的值。 
    
 _ppMsgEID_
  
> [输出]为其存储中的对象的返回的项标识符字符串指针的指针。 如果_szMsgID_参数指向的非复合条目标识符， _ppMsgEID_指向到非复合项标识符的转换后副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果复合_szMsgID_参数指定的标识符，它是从 ASCII 转换，拆分成对象在其消息存储库中的项标识符和存储的项标识符。 只需转换并复制将非复合条目标识符字符串。 要分隔的复合标识符字符串通常是一个[HrComposeMsgID](hrcomposemsgid.md)函数创建。 
  
调用**HrDecomposeMsgID**函数等效于调用[HrEntryIDFromSz](hrentryidfromsz.md)函数，然后选择[HrDecomposeEID](hrdecomposeeid.md)函数。 
  

