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
# <a name="ifoldersupportgetsupportmask"></a><span data-ttu-id="b38bb-103">IFolderSupport::GetSupportMask</span><span class="sxs-lookup"><span data-stu-id="b38bb-103">IFolderSupport::GetSupportMask</span></span>

  
  
<span data-ttu-id="b38bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b38bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b38bb-105">获取共享文件夹的支持的信息。</span><span class="sxs-lookup"><span data-stu-id="b38bb-105">Gets information about a folder's support for sharing.</span></span>
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a><span data-ttu-id="b38bb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b38bb-106">Parameters</span></span>

 <span data-ttu-id="b38bb-107">_pdwSupportMask_</span><span class="sxs-lookup"><span data-stu-id="b38bb-107">_pdwSupportMask_</span></span>
  
> <span data-ttu-id="b38bb-108">[输出]表示文件夹是否支持共享的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b38bb-108">[out] A bitmask indicating if the folder supports sharing.</span></span>
    
 <span data-ttu-id="b38bb-109">**FS_NONE**</span><span class="sxs-lookup"><span data-stu-id="b38bb-109">**FS_NONE**</span></span>
  
> <span data-ttu-id="b38bb-110">指示该文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="b38bb-110">Indicates that the folder does not support sharing.</span></span>
    
 <span data-ttu-id="b38bb-111">**FS_SUPPORTS_SHARING**</span><span class="sxs-lookup"><span data-stu-id="b38bb-111">**FS_SUPPORTS_SHARING**</span></span>
  
> <span data-ttu-id="b38bb-112">指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="b38bb-112">Indicates that the folder supports sharing.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b38bb-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b38bb-113">Return value</span></span>

<span data-ttu-id="b38bb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b38bb-114">S_OK</span></span> 
  
> <span data-ttu-id="b38bb-115">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b38bb-115">The call was successful.</span></span>
    

