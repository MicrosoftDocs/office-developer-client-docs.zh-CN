---
title: UPMOV
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 098743a5-f265-639a-8ba6-1412705bee0a
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: a7588d5fed2e059be7e628d8a76a12f76aea734d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339184"
---
# <a name="upmov"></a>UPMOV
 
**适用于**：Outlook 2013 | Outlook 2016 
  
有关上载已移动项目的信息。 此信息在[上载删除状态状态](upload-delete-status-state.md)和[上传表状态](upload-table-state.md)期间使用。
  
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

## <a name="members"></a>成员

_ulFlags_
  
> 实时用于在上载过程中确定相应行为的标志。
    
  - UPV_ERROR
    
    - 实时打开服务器文件夹时出现问题。
    
  - UPV_DIRTY
    
    - 实时上载状态已更改。 客户端使用它来跟踪本地存储的状态更改。
    
  - UPV_COMMIT
    
    - 实时提交上载状态。
    
_保护_
  
>  [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pstmReserved_
  
>  [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pszName_
  
>  排除目标文件夹的名称。 
    
  > [!NOTE]
  > 此成员不支持 UNICODE。 
  
_feid_
  
>  排除目标文件夹的条目 ID。 
    
_pfld_
  
>  实时指向服务器文件夹的指针。 
    
_pxicc_
  
>  实时指向**IExchangeImportContentsChanges** content 接口的指针, 该接口支持在使用增量更改同步 (ICS) 时上载内容更改。 有关**IExchangeImportContentsChanges**和 ICS 的详细信息, 请参阅[ICS 评估标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
    
_dwReserved_
  
>  [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pupmovNext_
  
>  排除下一个移动上下文。 
    
_cEntMov_
  
>  实时此处移动的项目数。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [FEID](feid.md)

