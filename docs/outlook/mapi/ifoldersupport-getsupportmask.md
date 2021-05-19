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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1c27bdc52ebe725c40cbf318fab0678f41cdc287
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417369"
---
# <a name="ifoldersupportgetsupportmask"></a>IFolderSupport::GetSupportMask

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取文件夹对共享的支持信息。
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a>参数

 _pdwSupportMask_
  
> [out]指示文件夹是否支持共享的位掩码。
    
 **FS_NONE**
  
> 指示文件夹不支持共享。
    
 **FS_SUPPORTS_SHARING**
  
> 指示文件夹支持共享。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功。
    

