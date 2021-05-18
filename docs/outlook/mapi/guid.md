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
ms.openlocfilehash: 12c50ab5936d7fffd364c276ba07ca69d3459ae7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421583"
---
# <a name="guid"></a>GUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 GUID (全局唯) 。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiguid.h  <br/> |
   
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
  
> 无符号长整型数据值。
    
 **Data2**
  
> 无符号短整型数据值。
    
 **Data3**
  
> 无符号短整型数据值。
    
 **Data4**
  
> 无符号字符数组。
    
## <a name="remarks"></a>备注

 **在 MAPI** 中按如下方式使用 GUID 结构： 
  
- 在唯一标识服务提供商的 [MAPIUID](mapiuid.md) 结构中。 
    
- 对于接口标识符。
    
- 在命名属性的属性集名称中。 
    
邮件存储和通讯簿提供程序生成要用于 **其 MAPIUID** 结构的 **GUID** 结构。 通过将生成的 **MAPIUID** 传递到 [IMAPISupport：：SetProviderUID，](imapisupport-setprovideruid.md)这些服务提供商会通知 MAPI 它们的唯一标识符。
  
此外，它们还用于实现 Microsoft Remote Procedure Call (RPC) 和 Object Description Language (ODL) 。 有关这些用法详细信息，请参阅 *《Microsoft RPC* 程序员指南和参考》、OLE 程序员参考和 Inside *OLE，**第二版*。  
  
**GUID** 结构在 *Win32 程序员参考中定义*。 MAPI 中使用的 **GUID** 结构的特定值在 MAPI 头文件 Mapiguid.h 中定义。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)


[MAPI 结构](mapi-structures.md)

