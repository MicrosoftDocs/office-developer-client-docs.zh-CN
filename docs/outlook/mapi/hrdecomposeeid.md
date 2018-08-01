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
ms.openlocfilehash: e66d48b6caefe0fee67f41ea829db3201751cf27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775160"
---
# <a name="hrdecomposeeid"></a>HrDecomposeEID

  
  
**适用于**： Outlook 
  
将一个对象，通常一条消息的消息存储的复合条目标识符分为存储区中对象的项标识符和存储的项标识符。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]加入会话，使用客户端应用程序的指针。 
    
 _cbEID_
  
> [in]大小 （以字节为单位的复合条目标识符来分隔）。 
    
 _pEID_
  
> [in]指向要分隔的复合项标识符的指针。 
    
 _pcbStoreEID_
  
> [输出]指向返回的大小，以字节为单位的项标识符的消息存储库包含对象的指针。 如果_pEID_参数指向的非复合条目标识符， _pcbStoreEID_参数指向值为零。 
    
 _ppStoreEID_
  
> [输出]为返回的项标识符的消息存储库包含对象的指针的指针。 如果_pEID_参数指向的非复合条目标识符，则_ppStoreEID_参数中返回 NULL。 
    
 _pcbMsgEID_
  
> [输出]指向返回的大小，以字节为单位的对象的项标识符的指针。 如果_pEID_参数指向的非复合条目标识符， _pcbMsgEID_参数等于_cbEID_参数的值。 
    
 _ppMsgEID_
  
> [输出]指向与返回的项标识符的对象的指针的指针。 如果_pEID_参数指向的非复合条目标识符， _ppMsgEID_指向到非复合项标识符的副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果复合_pEID_参数指定的标识符，它被拆分对象在其消息存储库中的项标识符和存储的项标识符。 非复合条目标识符字符串是简单复制。 要分隔的复合标识符通常是一个[HrComposeEID](hrcomposeeid.md)函数创建。 
  
## <a name="notes-to-callers"></a>给调用方的说明

成功完成此函数时释放保留_pEID_参数的内存。 调用实现负责释放内存输出参数。 
  

