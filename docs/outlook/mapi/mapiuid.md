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
  
用于唯一标识服务提供程序的[GUID](guid.md)结构的字节顺序独立版本。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[IsEqualMAPIUID](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a>Members

 **ab**
  
> 包含16字节标识符的数组。
    
## <a name="remarks"></a>说明

**MAPIUID**结构是一个添加到英特尔®处理器字节顺序的**GUID**结构。 
  
MAPI 创建**MAPIUID**结构的方式非常少导致两个不同的项具有相同的标识符。 **MAPIUID**结构可以存储为二进制属性或文件, 而无需考虑存储或访问信息的计算机的字节排序。 
  
 使用**MAPIUID**结构: 
  
- 标识配置文件部分。
    
- 在邮件存储区和通讯簿对象的条目标识符中, 用于标识负责的服务提供程序。
    
- 在邮件的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。
    
若要生成搜索密钥的**MAPIUID**标识符, 服务提供程序调用[IMAPISupport:: NewUID](imapisupport-newuid.md)。
  
当客户端通过网络传输邮件时, 它应使用不会更改**MAPIUID**数据字节顺序的协议或传输格式。 
  
有关如何使用**MAPIUID**结构的详细信息, 请参阅下列主题: 
  
[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)
  
[设置传输顺序](setting-transport-order.md)
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IMAPISupport::NewUID](imapisupport-newuid.md)


[MAPI 结构](mapi-structures.md)

