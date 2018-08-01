---
title: IFolderSupportGetSupportMask
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IFolderSupport.GetSupportMask
api_type:
- COM
ms.assetid: 8d8aaeb7-57d7-ba4c-95d1-a5368cfc4afe
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6f7aa23606da40c817c9af623b8bade9383ce427
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775305"
---
# <a name="ifoldersupportgetsupportmask"></a>IFolderSupport::GetSupportMask

  
  
**适用于**： Outlook 
  
获取共享文件夹的支持的信息。
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a>参数

 _pdwSupportMask_
  
> [输出]表示文件夹是否支持共享的位掩码。
    
 **FS_NONE**
  
> 指示该文件夹不支持共享。
    
 **FS_SUPPORTS_SHARING**
  
> 指示文件夹支持共享。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功。
    

