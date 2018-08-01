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
# <a name="ifoldersupportgetsupportmask"></a><span data-ttu-id="9d197-103">IFolderSupport::GetSupportMask</span><span class="sxs-lookup"><span data-stu-id="9d197-103">IFolderSupport::GetSupportMask</span></span>

  
  
<span data-ttu-id="9d197-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9d197-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9d197-105">获取共享文件夹的支持的信息。</span><span class="sxs-lookup"><span data-stu-id="9d197-105">Gets information about a folder's support for sharing.</span></span>
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a><span data-ttu-id="9d197-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d197-106">Parameters</span></span>

 <span data-ttu-id="9d197-107">_pdwSupportMask_</span><span class="sxs-lookup"><span data-stu-id="9d197-107">_pdwSupportMask_</span></span>
  
> <span data-ttu-id="9d197-108">[输出]表示文件夹是否支持共享的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9d197-108">[out] A bitmask indicating if the folder supports sharing.</span></span>
    
 <span data-ttu-id="9d197-109">**FS_NONE**</span><span class="sxs-lookup"><span data-stu-id="9d197-109">**FS_NONE**</span></span>
  
> <span data-ttu-id="9d197-110">指示该文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="9d197-110">Indicates that the folder does not support sharing.</span></span>
    
 <span data-ttu-id="9d197-111">**FS_SUPPORTS_SHARING**</span><span class="sxs-lookup"><span data-stu-id="9d197-111">**FS_SUPPORTS_SHARING**</span></span>
  
> <span data-ttu-id="9d197-112">指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="9d197-112">Indicates that the folder supports sharing.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9d197-113">返回值</span><span class="sxs-lookup"><span data-stu-id="9d197-113">Return value</span></span>

<span data-ttu-id="9d197-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d197-114">S_OK</span></span> 
  
> <span data-ttu-id="9d197-115">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="9d197-115">The call was successful.</span></span>
    

