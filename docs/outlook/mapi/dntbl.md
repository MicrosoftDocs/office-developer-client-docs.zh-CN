---
title: DNTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 77835b48-43aa-8518-9712-754e84f1e713
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 4716a6f42968d7451a5db36173c4e6a9e843c08e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337000"
---
# <a name="dntbl"></a>DNTBL
 
**适用于**：Outlook 2013 | Outlook 2016 
  
在[下载表状态](download-table-state.md)期间从服务器下载文件夹内容的信息，作为存储上内容完全同步的一部分。
  
## <a name="quick-info"></a>快速信息

```cpp
struct DNTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved1; 
    LPSTREAM pstmReserved2; 
    LPSTREAM pstmReserved3; 
    LPSTREAM pstmReserved4; 
    PXICC pxicc; 
    PXIHC pxihc; 
    LPSTR pszName; 
    FILETIME ftLastMod; 
    ULONG ulRights; 
    FEID feid; 
    UINT uintReserved; 
    DNTBLE rgte[2]; 
    LPSRestriction psrReserved; 
    BOOL boReserved; 
    void* pReserved1; 
    void* pReserved2; 
};

```

## <a name="members"></a>成员

_ulFlags_
  
> [传入] 修改行为的标签 
    
  - DNT_OK
    
    - [传入] 下载成功。 客户端从服务器下载信息之后对此进行设置。
    
_pstmReserved1_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pstmReserved2_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pstmReserved3_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pstmReserved4_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pxicc_
  
>  [传出] 指向支持下载内容更改的 **IExchangeImportContentsChanges** 内容界面的指针。 有关 **IExchangeImportContentsChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_pxihc_
  
>  [传出] 指向支持下载增量层次结构更改的 **IExchangeImportHierarchyChanges** 层次结构界面的指针。 有关 **IExchangeImportHierarchyChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_pszName_
  
>  [传出] 文件夹的名称。 
    
_ftLastMod_
  
>  [传出] 文件夹的上次修改时间。 
    
_ulRights_
  
>  [传出] 文件夹的 **[PR_RIGHTS](https://msdn.microsoft.com/library/ee238052%28v=EXCHG.80%29.aspx)** 属性的值。 
    
_feid_
  
>  [传出] 文件夹的条目 ID。 
    
_uintReserved_
  
>  [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_rgte_
  
> [传出] 普通（或非隐藏）和关联（或隐藏）项的更改。  *rgte[0]* 用于普通项，*rgte[1]* 用于关联项。 Outlook 在下载期间使用增量更改同步 (ICS) 填充此成员。 有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_lpsrReserved_
  
>  [传入] /[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_boReserved_
  
>  [传入] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pReserved1_
  
>  [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pReserved2_
  
>  [传入] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
## <a name="see-also"></a>另请参阅

- [关于复制状态机](about-the-replication-state-machine.md)  
- [MAPI 常量](mapi-constants.md) 
- [DNTBLE](dntble.md)

