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
ms.openlocfilehash: e47f4e0d1ab9ab3ecfd53932b8ef26440134c603
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407240"
---
# <a name="flatentry"></a>FLATENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
[ENTRYID](entryid.md)结构加上指定 **ENTRYID** 结构大小的字节计数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[cbFLATENTRY](cbflatentry.md) [、CbNewFLATENTRY](cbnewflatentry.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} FLATENTRY, FAR *LPFLATENTRY;

```

## <a name="members"></a>Members

 **cb**
  
> **abEntry** 成员中的字节数。 
    
 **abEntry**
  
> 包含标志和二进制数据数组的完整条目标识符。
    
## <a name="remarks"></a>备注

**FLATENTRY** 结构类似于 [ENTRYID](entryid.md)结构。 但是，存在一些差异： 
  
- **FLATENTRY** 结构存储条目标识符的大小;**ENTRYID** 不会。 
    
- **FLATENTRY** 结构将标志数据与条目标识符的其余部分一起存储;**ENTRYID** 单独存储它们。 
    
- **FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中，**而 ENTRYID** 结构由 [IMAPIProp](imapipropiunknown.md)接口方法和以下 **OpenEntry** 方法使用 [：IABLogon：：OpenEntry](iablogon-openentry.md)和 [IAddrBook ：：OpenEntry](iaddrbook-openentry.md)、 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md)、 [IMAPISession：：OpenEntry](imapisession-openentry.md)、 [IMAPISupport：：OpenEntry](imapisupport-openentry.md)、 [IMsgStore：：OpenEntry](imsgstore-openentry.md)、 [IMSLogon：：OpenEntry](imslogon-openentry.md)
    
- **FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中。 **ENTRYID** 结构用于在磁盘上存储条目标识符。 
    
## <a name="see-also"></a>另请参阅



[ENTRYID](entryid.md)


[MAPI 结构](mapi-structures.md)

