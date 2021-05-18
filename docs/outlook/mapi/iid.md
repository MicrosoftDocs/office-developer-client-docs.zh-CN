---
title: IID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IID
api_type:
- COM
ms.assetid: fa5498ab-2f8a-42f8-ba9d-1d555768594f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5605de7dbcc18197748713bcf909839690d7259f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411594"
---
# <a name="iid"></a>IID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用于描述 MAPI 接口标识符的 [GUID](guid.md) 结构。 
  
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

请参阅 **GUID** 结构。 
  
## <a name="remarks"></a>备注

**IID** 结构用于唯一标识 MAPI 接口并将特定接口与对象关联。 例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md)打开文件夹时，客户端将 _lpInterface_ 参数设置为指向表示 [IMAPIFolder](imapifolderimapicontainer.md)接口的 **IID。** MAPI 定义 **要存储的 IMAPIFolderIID** IID_IMAPIFolder。 **IID** 结构还用于唯一标识 OLE 接口。 
  
MAPI 接口的所有特定 **IID** 结构在 Mapiguid.h 头文件中定义。 
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)


[MAPI 结构](mapi-structures.md)

