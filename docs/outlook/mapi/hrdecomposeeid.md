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
  
将对象的复合条目标识符 (通常是邮件存储区中的邮件) 分隔到存储区中该对象的条目标识符和存储的条目标识符中。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
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
  
> 实时指向客户端应用程序正在使用的会话的指针。 
    
 _cbEID_
  
> 实时要分隔的复合条目标识符的大小 (以字节为单位)。 
    
 _pEID_
  
> 实时指向要分隔的复合条目标识符的指针。 
    
 _pcbStoreEID_
  
> 排除指向包含该对象的邮件存储区的条目标识符的返回大小 (以字节为单位)。 如果_pEID_参数指向 noncompound 条目标识符, 则_pcbStoreEID_参数将指向值0。 
    
 _ppStoreEID_
  
> 排除指向指向包含该对象的邮件存储区的返回项标识符的指针的指针。 如果_pEID_参数指向 noncompound 条目标识符, 则在_ppStoreEID_参数中返回 NULL。 
    
 _pcbMsgEID_
  
> 排除指向对象的条目标识符的返回大小 (以字节为单位) 的指针。 如果_pEID_参数指向 noncompound 条目标识符, 则_pcbMsgEID_参数等于_cbEID_参数的值。 
    
 _ppMsgEID_
  
> 排除指向指向对象的返回项标识符的指针的指针。 如果_pEID_参数指向 noncompound 条目标识符, 则_ppMsgEID_会指向指向 noncompound 条目标识符副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果_pEID_参数指定的标识符是复合的, 则会将其拆分为其邮件存储区中的对象的条目标识符和存储的条目标识符。 Noncompound 条目标识符字符串只是复制的。 要分隔的复合标识符通常是由[HrComposeEID](hrcomposeeid.md)函数创建的。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在成功完成此函数后, 将释放保留_pEID_参数的内存。 调用实现负责为输出参数释放内存。 
  

