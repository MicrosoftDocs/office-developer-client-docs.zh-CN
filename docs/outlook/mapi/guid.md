---
title: GUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GUID
api_type:
- COM
ms.assetid: e3608c47-06be-4476-a6ef-060fac252387
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08ecb718572944db07c2888e0aae1464bd5c0f98
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775047"
---
# <a name="guid"></a>GUID

  
  
**适用于**： Outlook 
  
介绍的全局唯一标识符 (GUID)。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiguid.h  <br/> |
   
```cpp
typedef struct _GUID
{
  unsigned long Data1;
  unsigned short Data2;
  unsigned short Data3;
  unsigned char Data4[8];
} GUID;

```

## <a name="members"></a>Members

 **Data1**
  
> 无符号的长整型数据值。
    
 **Data2**
  
> 无符号短整数数据值。
    
 **Data3**
  
> 无符号短整数数据值。
    
 **Data4**
  
> 无符号字符数组。
    
## <a name="remarks"></a>说明

 **GUID**结构中将使用 MAPI，如下所示： 
  
- [MAPIUID](mapiuid.md)结构中的唯一标识服务提供商。 
    
- 接口标识符。
    
- 属性中设置命名属性的名称。 
    
消息存储和地址簿提供程序生成的**GUID**结构使用其**MAPIUID**结构中。 通过将生成**MAPIUID**传递给[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)，这些服务提供商告知 MAPI，其唯一标识符。
  
另外，他们的 Microsoft 远程过程调用 (RPC) 和对象描述语言 (ODL) 实现中使用。 有关这些使用的详细信息，请参阅*Microsoft RPC 程序员指南和参考 （英文）*、 *OLE 程序员参考*和*内部 OLE*，*第二版*。 
  
**GUID**结构是*Win32 程序员参考*中定义的。 MAPI 头文件 Mapiguid.h 中定义的**GUID**结构 MAPI 内使用的特定值。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)


[MAPI 结构](mapi-structures.md)

