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
# <a name="ifoldersupportgetsupportmask"></a><span data-ttu-id="b2d60-103">IFolderSupport::GetSupportMask</span><span class="sxs-lookup"><span data-stu-id="b2d60-103">IFolderSupport::GetSupportMask</span></span>

  
  
<span data-ttu-id="b2d60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2d60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2d60-105">获取文件夹对共享的支持信息。</span><span class="sxs-lookup"><span data-stu-id="b2d60-105">Gets information about a folder's support for sharing.</span></span>
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a><span data-ttu-id="b2d60-106">参数</span><span class="sxs-lookup"><span data-stu-id="b2d60-106">Parameters</span></span>

 <span data-ttu-id="b2d60-107">_pdwSupportMask_</span><span class="sxs-lookup"><span data-stu-id="b2d60-107">_pdwSupportMask_</span></span>
  
> <span data-ttu-id="b2d60-108">[out]指示文件夹是否支持共享的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b2d60-108">[out] A bitmask indicating if the folder supports sharing.</span></span>
    
 <span data-ttu-id="b2d60-109">**FS_NONE**</span><span class="sxs-lookup"><span data-stu-id="b2d60-109">**FS_NONE**</span></span>
  
> <span data-ttu-id="b2d60-110">指示文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="b2d60-110">Indicates that the folder does not support sharing.</span></span>
    
 <span data-ttu-id="b2d60-111">**FS_SUPPORTS_SHARING**</span><span class="sxs-lookup"><span data-stu-id="b2d60-111">**FS_SUPPORTS_SHARING**</span></span>
  
> <span data-ttu-id="b2d60-112">指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="b2d60-112">Indicates that the folder supports sharing.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b2d60-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b2d60-113">Return value</span></span>

<span data-ttu-id="b2d60-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2d60-114">S_OK</span></span> 
  
> <span data-ttu-id="b2d60-115">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b2d60-115">The call was successful.</span></span>
    

