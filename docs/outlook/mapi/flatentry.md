---
title: FLATENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATENTRY
api_type:
- COM
ms.assetid: 03e53e08-9113-4101-84c9-ccf6d43127f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2f5f4d50b085c437d1caab5f70dcb741afe090bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774938"
---
# <a name="flatentry"></a>FLATENTRY

  
  
**适用于**： Outlook 
  
[ENTRYID](entryid.md)结构加上指定**ENTRYID**结构大小的字节数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[cbFLATENTRY](cbflatentry.md) [CbNewFLATENTRY](cbnewflatentry.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} FLATENTRY, FAR *LPFLATENTRY;

```

## <a name="members"></a>Members

 **cb**
  
> **AbEntry**成员中的字节数。 
    
 **abEntry**
  
> 包含数组标志和二进制数据的完整输入标识符。
    
## <a name="remarks"></a>说明

**FLATENTRY**结构类似于[ENTRYID](entryid.md)结构。 但是，有一些区别： 
  
- **FLATENTRY**结构存储的项标识符; 的大小未为**ENTRYID** 。 
    
- **FLATENTRY**结构将一起条目标识符; 的其余部分标志数据存储**ENTRYID**单独存储这些。 
    
- **FLATENTRY**结构用于存储在文件中的项标识符或而[IMAPIProp](imapipropiunknown.md)接口方法和以下**OpenEntry**方法使用**ENTRYID**结构中的字节流传递： [IABLogon:: OpenEntry](iablogon-openentry.md)， [IAddrBook::OpenEntry](iaddrbook-openentry.md)、 [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、 [IMAPISession::OpenEntry](imapisession-openentry.md)、 [IMAPISupport::OpenEntry](imapisupport-openentry.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)、 [IMSLogon::OpenEntry](imslogon-openentry.md)
    
- **FLATENTRY**结构用于存储在文件中的项标识符，或将其传递中的字节流。 **ENTRYID**结构用于存储在磁盘上的项标识符。 
    
## <a name="see-also"></a>另请参阅



[ENTRYID](entryid.md)


[MAPI 结构](mapi-structures.md)

