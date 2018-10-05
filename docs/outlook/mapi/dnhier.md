---
title: DNHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3953dc9d-0146-3689-63f0-c6ba78566b8b
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 06f30b4856fc10127aec99975652e28a5e8dda30
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389083"
---
# <a name="dnhier"></a>DNHIER

**适用于**：Outlook 2013 | Outlook 2016 
  
层次结构从服务器下载过程中[下载层次结构状态](download-hierarchy-state.md)，这完整的层次结构同步的信息。 此下载的过程使用 Microsoft Exchange 增量更改同步 (ICS)。 ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct DNHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    PXIHC pxihc; 
    UINT cEntNew; 
   UINT cEntMod; 
    UINT cEntDel; 
};
```

## <a name="members"></a>Members

_ulFlags_
  
>  [in]若要下载过程确定适当的行为的标志。 
    
   - DNH_OK
    
   - [in]下载成功。 客户端设置从服务器下载信息之后。
    
_pstmReserved_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pxihc_
  
>  [输出]支持下载增量层次结构更改的**IExchangeImportHierarchyChanges**层次结构接口的指针。 **IExchangeImportHierarchyChanges**的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_cEntNew_
  
> [输出]添加到本地存储的文件夹的数量。 Outlook 时使用 ICS 下载期间填充此值。
    
_cEntMod_
  
> [输出]文件夹上的本地存储修改数。 Outlook 时使用 ICS 下载期间填充此值。
    
_cEntDel_
  
> [输出]要删除对本地存储的文件夹的数量。 Outlook 时使用 ICS 下载期间填充此值。
    
## <a name="see-also"></a>另请参阅

- [关于复制状态计算机](about-the-replication-state-machine.md) 
- [MAPI 常量](mapi-constants.md)

