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
ms.openlocfilehash: 3bcad4c236f71390f7a048eb66860720e9180e06
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582040"
---
# <a name="hrcomposemsgid"></a>HrComposeMsgID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建表示一个对象，通常一条消息的消息存储的复合条目标识符 ASCII 字符串。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]加入会话，使用客户端应用程序的指针。 
    
 _cbStoreRecordKey_
  
> [in]大小 （以字节为单位，消息存储库包含邮件或其他对象的记录项）。 如果_cbStoreRecordKey_参数中传递零，则该_pszMsgID_参数指向副本的项标识符的转换为文本。 
    
 _pStoreRecordKey_
  
> [in]向记录项的消息存储库包含邮件或其他对象的指针。 
    
 _cbMsgEID_
  
> [in]大小，以字节为单位的项标识符的邮件或其他对象。 
    
 _pMsgEID_
  
> [in]指向对象的项标识符的指针。 
    
 _pszMsgID_
  
> [输出]指向返回 ASCII 字符串。 如果_cbStoreRecordKey_参数大于零，为复合项标识符的_pszMsgID_参数点转换为文本。 如果_cbStoreRecordKey_为零，为非复合条目标识符_pszMsgID_磅转换为文本。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果邮件或其他对象为其创建的复合条目标识符位于的消息存储，标识符字符串创建从对象的项标识符的存储记录的键。 如果对象不是存储区中，即，如果_cbStoreRecordKey_参数中传递的存储记录密钥的字节数为零，对象的项标识符只需复制并转换为字符串。 
  
调用**HrComposeMsgID**函数等效于调用[HrComposeEID](hrcomposeeid.md)函数，然后选择[HrSzFromEntryID](hrszfromentryid.md)函数。 
  
 **HrComposeMsgID**使客户端应用程序以使用复合条目标识符使用的多个存储区中的对象。 应用程序可以调用[HrDecomposeMsgID](hrdecomposemsgid.md)函数拆分到其原始构成的复合条目标识符。 
  

