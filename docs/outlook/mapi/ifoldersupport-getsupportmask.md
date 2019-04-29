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
# <a name="ifoldersupportgetsupportmask"></a><span data-ttu-id="e110b-103">IFolderSupport::GetSupportMask</span><span class="sxs-lookup"><span data-stu-id="e110b-103">IFolderSupport::GetSupportMask</span></span>

  
  
<span data-ttu-id="e110b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e110b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e110b-105">获取有关文件夹支持共享的信息。</span><span class="sxs-lookup"><span data-stu-id="e110b-105">Gets information about a folder's support for sharing.</span></span>
  
```cpp
HRESULT GetSupportMask( 
    DWORD * pdwSupportMask 
); 
```

## <a name="parameters"></a><span data-ttu-id="e110b-106">参数</span><span class="sxs-lookup"><span data-stu-id="e110b-106">Parameters</span></span>

 <span data-ttu-id="e110b-107">_pdwSupportMask_</span><span class="sxs-lookup"><span data-stu-id="e110b-107">_pdwSupportMask_</span></span>
  
> <span data-ttu-id="e110b-108">排除表示文件夹是否支持共享的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e110b-108">[out] A bitmask indicating if the folder supports sharing.</span></span>
    
 <span data-ttu-id="e110b-109">**FS_NONE**</span><span class="sxs-lookup"><span data-stu-id="e110b-109">**FS_NONE**</span></span>
  
> <span data-ttu-id="e110b-110">指示文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="e110b-110">Indicates that the folder does not support sharing.</span></span>
    
 <span data-ttu-id="e110b-111">**FS_SUPPORTS_SHARING**</span><span class="sxs-lookup"><span data-stu-id="e110b-111">**FS_SUPPORTS_SHARING**</span></span>
  
> <span data-ttu-id="e110b-112">指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="e110b-112">Indicates that the folder supports sharing.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e110b-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e110b-113">Return value</span></span>

<span data-ttu-id="e110b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e110b-114">S_OK</span></span> 
  
> <span data-ttu-id="e110b-115">调用成功。</span><span class="sxs-lookup"><span data-stu-id="e110b-115">The call was successful.</span></span>
    

