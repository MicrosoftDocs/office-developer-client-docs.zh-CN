---
title: DNTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 77835b48-43aa-8518-9712-754e84f1e713
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 6096118d72dfc51fb60025a55f581ebf97b000a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774836"
---
# <a name="dntbl"></a>DNTBL
 
**适用于**： Outlook 
  
文件夹内容从服务器下载过程中[下载表状态](download-table-state.md)，存储区上的内容的完全同步的一部分的信息。
  
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

## <a name="members"></a>Members

_ulFlags_
  
> [in]若要修改行为的标志 
    
  - DNT_OK
    
    - [in]下载成功。 客户端设置从服务器下载信息之后。
    
_pstmReserved1_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pstmReserved2_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pstmReserved3_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pstmReserved4_
  
> [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pxicc_
  
>  [输出]支持下载内容更改的**IExchangeImportContentsChanges**内容接口的指针。 **IExchangeImportContentsChanges**的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。
    
_pxihc_
  
>  [输出]支持下载增量层次结构更改的**IExchangeImportHierarchyChanges**层次结构接口的指针。 **IExchangeImportHierarchyChanges**的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。
    
_pszName_
  
>  [输出]文件夹的名称。 
    
_ftLastMod_
  
>  [输出]文件夹的上次修改时间。 
    
_ulRights_
  
>  [输出]文件夹的**[PR_RIGHTS](http://msdn.microsoft.com/en-us/library/ee238052%28v=EXCHG.80%29.aspx)** 属性的值。 
    
_feid_
  
>  [输出]文件夹的条目 ID。 
    
_uintReserved_
  
>  [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_rgte_
  
> [输出]普通 （或非隐藏） 的更改和关联 （或隐藏） 的项目。  *rgte [0]* 的普通项目， *rgte [1]* 用于关联的项目。 Outlook 时使用增量更改同步 (ICS) 下载期间填充此成员。 ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。
    
_lpsrReserved_
  
>  [in] / [输出] 此成员保留供内部使用的 Outlook，不支持。 
    
_boReserved_
  
>  [in]此成员仅供内部使用的 Outlook，不支持。 
    
_pReserved1_
  
>  [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pReserved2_
  
>  [in]此成员仅供内部使用的 Outlook，不支持。 
    
## <a name="see-also"></a>另请参阅

- [关于复制状态计算机](about-the-replication-state-machine.md)  
- [MAPI 常量](mapi-constants.md) 
- [DNTBLE](dntble.md)

