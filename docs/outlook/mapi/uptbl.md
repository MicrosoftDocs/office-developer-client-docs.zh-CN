---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 70d23bebfda10339ffb05f573c8c309a44f09d7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779083"
---
# <a name="uptbl"></a>UPTBL

**适用于**： Outlook 
  
用于[上载表状态](upload-table-state.md)期间上载文件夹的内容的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    LPSTR pszName; 
    FEID feid; 
    UINT uintReserved; 
    UPTBLE rgte[2]; 
    UINT iEnt; 
    UINT cEnt; 
    PUPMOV pupmovHead; 
    void* pReserved; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> [in]若要在上载过程中确定适当的行为的标志。
    
  - UPT_OK
    
    - [in]上载成功。 客户端设置后将文件夹内容上载到服务器。
    
_pstmReserved_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pszName_
  
> [输出]文件夹的名称。
    
_feid_
  
> [输出]文件夹的条目 ID。
    
_uintReserved_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_rgte_
  
> [输出]结构的文件夹中保留的正常 （或非隐藏） 项和关联 （或隐藏） 的项的以下信息： _rgte [0]_ 是正常的项目，并且_rgte [1]_ 关联的项目。 
    
   - 新的或修改项的数目
   - 读取项的数目 
   - 已删除的项的数目
    
 _iEnt_
  
> [输出]要跟踪上载更改由 _%_ 指定数量的索引。
    
_%_
  
> [输出]更改应用于文件夹的数量。
    
_pupmovHead_
  
> [输出][UPMOV](upmov.md)结构的链。 
    
_保留_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。
    
## <a name="see-also"></a>另请参阅

- [有关复制 API](about-the-replication-api.md)
- [有关的复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPTBLE](uptble.md)

