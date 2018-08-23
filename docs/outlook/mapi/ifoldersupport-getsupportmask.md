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
ms.openlocfilehash: c51f4a7266e67be08f31daa5afbf23ce0b256252
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567851"
---
# <a name="ifoldersupportgetsupportmask"></a>IFolderSupport::GetSupportMask

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
    

