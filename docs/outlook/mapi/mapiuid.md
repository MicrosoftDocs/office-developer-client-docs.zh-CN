---
title: MAPIUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIUID
api_type:
- COM
ms.assetid: 63eac3ee-e59b-4a06-8bb9-f72764d84bda
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da314205f7d2dd746b72aa7e2b5ff2a13bb0c21b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432203"
---
# <a name="mapiuid"></a>MAPIUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
GUID 结构的独立字节顺序版本，[](guid.md)用于唯一标识服务提供商。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[IsEqualMAPIUID](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a>Members

 **ab**
  
> 包含 16 字节标识符的数组。
    
## <a name="remarks"></a>备注

**MAPIUID** 结构是一种 **GUID** 结构，®处理器字节顺序。 
  
MAPI 创建 **MAPIUID** 结构的方式使得两个不同的项具有相同的标识符非常少见。 **MAPIUID** 结构可以存储为二进制属性或文件，而不考虑计算机存储或访问信息的字节顺序。 
  
 **使用 MAPIUID** 结构： 
  
- 标识配置文件部分。
    
- 在邮件存储和通讯簿对象的条目标识符中，以标识负责的服务提供商。
    
- In the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of messages.
    
若要为搜索密钥 **生成 MAPIUID** 标识符，服务提供商调用 [IMAPISupport：：NewUID](imapisupport-newuid.md)。
  
当客户端跨网络传输邮件时，它应当使用不更改 **MAPIUID** 数据的字节顺序的协议或传输格式。 
  
有关如何使用 **MAPIUID** 结构的信息，请参阅下列主题： 
  
[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)
  
[设置传输顺序](setting-transport-order.md)
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IMAPISupport::NewUID](imapisupport-newuid.md)


[MAPI 结构](mapi-structures.md)

