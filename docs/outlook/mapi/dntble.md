---
title: DNTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 10fb1650-6c3e-f467-91cd-48e5ddd82827
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: d92e8d7b3fb14051ffceb829f3df3f6fa12e6e23
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565856"
---
# <a name="dntble"></a>DNTBLE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在[下载表状态](download-table-state.md)期间，从服务器下载文件夹的内容的信息。 此下载的过程使用 Microsoft Exchange 增量更改同步 (ICS)。 ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct DNTBLE 
{ 
    UINT cEntNew; 
    UINT cEntMod; 
    UINT cEntRead; 
    UINT cEntDel; 
};
```

## <a name="members"></a>Members

 _cEntNew_
  
> [输出]添加到本地存储的项目数。 Outlook 时使用 ICS 下载期间填充此值。
    
 _cEntMod_
  
> [输出]修改对本地存储的项目数。 Outlook 时使用 ICS 下载期间填充此值。
    
 _cEntRead_
  
> [输出]读取或上本地存储标记为未读的项目数。 Outlook 时使用 ICS 下载期间填充此值。
    
 _cEntDel_
  
> [输出]对本地存储删除的项目数。 Outlook 时使用 ICS 下载期间填充此值。
    
## <a name="see-also"></a>另请参阅



[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[DNTBL](dntbl.md)

