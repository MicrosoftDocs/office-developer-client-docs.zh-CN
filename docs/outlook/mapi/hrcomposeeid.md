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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429045"
---
# <a name="hrcomposeeid"></a>HrComposeEID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为对象（通常是邮件存储中的邮件）创建复合条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
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
  
> [in]指向客户端应用程序使用的会话的指针。 
    
 _cbStoreRecordKey_
  
> [in]保留邮件或其他对象的邮件存储的记录键的大小（以字节为单位）。 如果在  _cbStoreRecordKey_ 参数中传递零，  _则 ppEID_ 参数指向对象的条目标识符的副本。 
    
 _pStoreRecordKey_
  
> [in]指向包含邮件或其他对象的邮件存储的记录键的指针。 
    
 _cbMsgEID_
  
> [in]邮件或其他对象的条目标识符的大小（以字节为单位）。 
    
 _pMsgEID_
  
> [in]指向对象的条目标识符的指针。 
    
 _·2013_
  
> [out]指向返回的标识符的大小（以字节为单位）的指针。 
    
 _ppEID_
  
> [out]指向返回的条目标识符的指针的指针。 如果  _cbStoreRecordKey_ 参数的值大于零，  _则 ppEID_ 参数指向指向所创建的复合条目标识符的指针。 如果  _cbStoreRecordKey_ 为零，  _则 ppEID_ 指向指向对象条目标识符副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果要创建复合条目标识符的邮件或其他对象驻留在邮件存储中，则从对象的条目标识符和存储的记录密钥创建标识符。 如果对象不在存储区中，即，如果在  _cbStoreRecordKey_ 中传递的存储记录密钥的字节计数为零，则只需复制对象的条目标识符。 
  
**HrComposeEID** 函数允许应用程序通过复合条目标识符处理多个存储区中的对象。 应用程序可以调用 [HrDecomposeEID](hrdecomposeeid.md) 函数将复合条目标识符拆分为原始组成部分。 
  
## <a name="see-also"></a>另请参阅



[HrComposeMsgID](hrcomposemsgid.md)
  
[HrDecomposeMsgID](hrdecomposemsgid.md)

