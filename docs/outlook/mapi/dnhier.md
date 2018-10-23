---
title: DNHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3953dc9d-0146-3689-63f0-c6ba78566b8b
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 06f30b4856fc10127aec99975652e28a5e8dda30
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389083"
---
# <a name="dnhier"></a>DNHIER

**适用于**：Outlook 2013 | Outlook 2016 
  
在[下载层次结构状态](download-hierarchy-state.md)期间从服务器下载层次结构的信息，这是完整层次结构同步的一部分。 这一下载过程使用 Microsoft Exchange 增量更改同步 (ICS)。 有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
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

## <a name="members"></a>成员

_ulFlags_
  
>  [传入] 用于确定下载期间的适当行为的标签。 
    
   - DNH_OK
    
   - [传入] 下载成功。 客户端从服务器下载信息之后对此进行设置。
    
_pstmReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pxihc_
  
>  [传出] 指向支持下载增量层次结构更改的 **IExchangeImportHierarchyChanges** 层次结构界面的指针。 有关 **IExchangeImportHierarchyChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_cEntNew_
  
> [传出] 添加到本地存储的文件夹的数量。 Outlook 在下载期间使用 ICS 时填充此值。
    
_cEntMod_
  
> [传出] 本地存储上要修改的文件夹数量。 Outlook 在下载期间使用 ICS 时填充此值。
    
_cEntDel_
  
> [传出] 本地存储上要删除的文件夹数量。 Outlook 在下载期间使用 ICS 时填充此值。
    
## <a name="see-also"></a>另请参阅

- [关于复制状态机](about-the-replication-state-machine.md) 
- [MAPI 常量](mapi-constants.md)

