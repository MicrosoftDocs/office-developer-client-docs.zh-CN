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
ms.openlocfilehash: f7ec60768ab07c56969f538f196a1f9df5dbed17
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587164"
---
# <a name="mapiuid"></a>MAPIUID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
用于唯一标识服务提供商的[GUID](guid.md)结构字节顺序独立版本。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[IsEqualMAPIUID](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a>Members

 **ab**
  
> 包含一个 16 字节标识符的数组。
    
## <a name="remarks"></a>注解

**MAPIUID**结构是置于 Intel® 处理器字节顺序的**GUID**结构。 
  
MAPI 以使它很少见这两个不同项具有相同标识符的一种创建**MAPIUID**结构。 可以存储**MAPIUID**结构中作为二进制属性或文件，而不考虑计算机存储或访问信息的字节排序。 
  
 使用**MAPIUID**结构： 
  
- 若要确定配置文件一节。
    
- 项标识符的消息中存储和通讯簿对象，用于标识负责服务提供商。
    
- 在邮件的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。
    
若要生成搜索关键字的**MAPIUID**标识符，服务提供商，请调用[IMAPISupport::NewUID](imapisupport-newuid.md)。
  
当客户端通过网络传输一条消息时，它应使用不会更改**MAPIUID**数据的字节顺序的协议或传输格式。 
  
有关如何使用**MAPIUID**结构的详细信息，请参阅以下主题： 
  
[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)
  
[设置传输顺序](setting-transport-order.md)
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IMAPISupport::NewUID](imapisupport-newuid.md)


[MAPI 结构](mapi-structures.md)

