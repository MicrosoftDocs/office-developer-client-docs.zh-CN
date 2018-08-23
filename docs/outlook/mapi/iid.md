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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00c7560427ece58026030ce6895d60aec7cc5a2e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570938"
---
# <a name="iid"></a>IID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍用于描述 MAPI 接口的标识符的[GUID](guid.md)结构。 
  
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

请参阅**GUID**结构。 
  
## <a name="remarks"></a>注解

**IID**结构用于唯一标识 MAPI 接口并将特定接口与对象相关联。 例如，当打开一个文件夹客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md) ，客户端将_lpInterface_参数设置为指向**IID**表示[IMAPIFolder](imapifolderimapicontainer.md)接口。 MAPI 定义**IMAPIFolderIID**为 IID_IMAPIFolder。 **IID**结构还用于唯一标识 OLE 接口。 
  
所有的 MAPI 接口的特定**IID**结构 Mapiguid.h 头文件中定义。 
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)


[MAPI 结构](mapi-structures.md)

