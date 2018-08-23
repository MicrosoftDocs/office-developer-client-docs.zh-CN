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
ms.openlocfilehash: 335fac38ff3f084195a000ad32a27adcb85c1cc6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564813"
---
# <a name="hrcomposeeid"></a>HrComposeEID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个对象，通常一条消息的消息存储的复合条目标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]加入会话，使用客户端应用程序的指针。 
    
 _cbStoreRecordKey_
  
> [in]大小 （以字节为单位，包含邮件或其他对象的消息存储的记录项）。 如果_cbStoreRecordKey_参数中传递零，则_ppEID_参数指向对象的项标识符的副本。 
    
 _pStoreRecordKey_
  
> [in]向记录项的消息存储库包含邮件或其他对象的指针。 
    
 _cbMsgEID_
  
> [in]大小，以字节为单位的项标识符的邮件或其他对象。 
    
 _pMsgEID_
  
> [in]指向对象的项标识符的指针。 
    
 _pcbEID_
  
> [输出]指向的大小，以字节为单位返回的标识符。 
    
 _ppEID_
  
> [输出]指向与返回的项标识符的指针的指针。 如果_cbStoreRecordKey_参数的值大于零， _ppEID_参数指向创建的复合项标识符的指针。 如果_cbStoreRecordKey_为零， _ppEID_指向到对象的项标识符的副本的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果邮件或其他对象为其创建的复合条目标识符位于邮件存储区，从对象的项标识符的存储记录键创建标识符。 如果对象不是存储区中，即，如果_cbStoreRecordKey_中传递的存储记录密钥的字节数为零，对象的项标识符是简单复制。 
  
**HrComposeEID**函数使应用程序以使用复合条目标识符使用的多个存储区中的对象。 应用程序可以调用[HrDecomposeEID](hrdecomposeeid.md)函数拆分到其原始构成的复合条目标识符。 
  
## <a name="see-also"></a>另请参阅



[HrComposeMsgID](hrcomposemsgid.md)
  
[HrDecomposeMsgID](hrdecomposemsgid.md)

