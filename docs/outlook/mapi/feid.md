---
title: FEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dde7eec-df3d-723c-db08-7ff0b6107a0b
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 3e534f91863e2a1300e03d112d1f532f486eedd9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588305"
---
# <a name="feid"></a>FEID

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
文件夹的标识符。 它包含的项标识符以及其他相关信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct FEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltid; 
};
```

## <a name="members"></a>Members

 _abFlags_
  
> 4 字节条目的文件夹的标识符。 有关 MAPI 项标识符的详细信息，请参阅**[ENTRYID](entryid.md)**。 
    
 _muid_
  
> 标识的存储提供程序的 GUID。 请参阅 mapidefs.h **MAPIUID**的类型定义。 
    
 _占位符_
  
> 此成员仅供内部使用的 Outlook，不支持。
    
 _ltid_
  
> 文件夹的长期 ID。
    
## <a name="see-also"></a>另请参阅



[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[LTID](ltid.md)
  
[UPFLD](upfld.md)
  
[SYNC](sync.md)

