---
title: UPMOV
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 098743a5-f265-639a-8ba6-1412705bee0a
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 43fd56932409861db86679eea6f1405dc4c37e62
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779056"
---
# <a name="upmov"></a>UPMOV
 
**适用于**： Outlook 
  
用于上载已移动的项目的信息。 [上载删除状态状态](upload-delete-status-state.md)和[上载表状态](upload-table-state.md)期间使用此信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPMOV 
{ 
      ULONG          ulFlags; 
      LPVOID         pReserved; 
      LPSTREAM       pstmReserved; 
      LPSTR          pszName; 
      FEID           feid; 
      LPMAPIFOLDER   pfld; 
      PXICC          pxicc; 
      DWORD          dwReserved; 
      PUPMOV         pupmovNext; 
      UINT           cEntMov; 
};
```

## <a name="members"></a>Members

_ulFlags_
  
> [in]若要在上载过程中确定适当的行为的标志。
    
  - UPV_ERROR
    
    - [in]打开服务器文件夹的问题。
    
  - UPV_DIRTY
    
    - [in]上载状态已更改。 客户端使用此跟踪状态本地存储中的更改。
    
  - UPV_COMMIT
    
    - [in]提交上载状态。
    
_保留_
  
>  [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pstmReserved_
  
>  [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pszName_
  
>  [输出]目标文件夹的名称。 
    
  > [!NOTE]
  > 此成员不支持 UNICODE。 
  
_feid_
  
>  [输出]目标文件夹的条目 ID。 
    
_pfld_
  
>  [in]指向服务器文件夹的指针。 
    
_pxicc_
  
>  [in]支持上载内容更改时使用增量更改同步 (ICS) 的**IExchangeImportContentsChanges**内容接口的指针。 **IExchangeImportContentsChanges**和 ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。
    
_dwReserved_
  
>  [输出]此成员仅供内部使用的 Outlook，不支持。 
    
_pupmovNext_
  
>  [输出]接下来移动上下文。 
    
_cEntMov_
  
>  [in]项目数移至此处。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [FEID](feid.md)

