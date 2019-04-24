---
title: HrComposeEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrComposeEID
api_type:
- COM
ms.assetid: 8aba90d8-ea1f-4636-af80-17bfeadbdfa0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7de4fdefee67c79fb15ac28f821b015cdda6708d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348060"
---
# <a name="hrcomposeeid"></a>HrComposeEID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为对象 (通常是邮件存储区中的邮件) 创建复合条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrComposeEID(
  LPMAPISESSION psession,
  ULONG cbStoreRecordKey,
  LPBYTE pStoreRecordKey,
  ULONG cbMsgEID,
  LPENTRYID pMsgEID,
  ULONG FAR * pcbEID,
  LPENTRYID FAR * ppEID
);
```

## <a name="parameters"></a>参数

 _psession_
  
> 实时指向客户端应用程序正在使用的会话的指针。 
    
 _cbStoreRecordKey_
  
> 实时包含邮件或其他对象的邮件存储区的记录键的大小 (以字节为单位)。 如果在_cbStoreRecordKey_参数中传递零, 则_ppEID_参数指向对象的条目标识符的副本。 
    
 _pStoreRecordKey_
  
> 实时指向邮件存储区中包含邮件或其他对象的记录键的指针。 
    
 _cbMsgEID_
  
> 实时邮件或其他对象的条目标识符的大小 (以字节为单位)。 
    
 _pMsgEID_
  
> 实时指向对象的条目标识符的指针。 
    
 _pcbEID_
  
> 排除指向返回的标识符的大小 (以字节为单位) 的指针。 
    
 _ppEID_
  
> 排除指向指向返回的条目标识符的指针的指针。 如果_cbStoreRecordKey_参数的值大于零, 则_ppEID_参数指向所创建的复合条目标识符的指针。 如果_cbStoreRecordKey_为零, 则_ppEID_指向指向对象的条目标识符副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果要为其创建复合条目标识符的邮件或其他对象驻留在邮件存储区中, 则将从该对象的条目标识符和存储的记录密钥创建该标识符。 如果对象不在 store 中 (即, 如果在_cbStoreRecordKey_中传递的存储记录键的字节数为零), 则只会复制该对象的条目标识符。 
  
**HrComposeEID**函数使应用程序能够通过使用复合条目标识符来处理多个存储中的对象。 应用程序可以调用[HrDecomposeEID](hrdecomposeeid.md)函数, 以将复合条目标识符拆分为其原始要素。 
  
## <a name="see-also"></a>另请参阅



[HrComposeMsgID](hrcomposemsgid.md)
  
[HrDecomposeMsgID](hrdecomposemsgid.md)

