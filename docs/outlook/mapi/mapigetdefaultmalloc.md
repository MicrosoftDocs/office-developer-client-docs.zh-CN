---
title: MAPIGetDefaultMalloc
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIGetDefaultMalloc
api_type:
- HeaderDef
ms.assetid: 148695dd-d886-4a06-9cfe-749059ae91ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 635f22c97ed27889245becbebb990ab3995b70b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438202"
---
# <a name="mapigetdefaultmalloc"></a><span data-ttu-id="3c83d-103">MAPIGetDefaultMalloc</span><span class="sxs-lookup"><span data-stu-id="3c83d-103">MAPIGetDefaultMalloc</span></span>

  
  
<span data-ttu-id="3c83d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3c83d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3c83d-105">检索默认 MAPI 内存分配函数的地址。</span><span class="sxs-lookup"><span data-stu-id="3c83d-105">Retrieves the address of the default MAPI memory allocation function.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3c83d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3c83d-106">Header file:</span></span>  <br/> |<span data-ttu-id="3c83d-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="3c83d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3c83d-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="3c83d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3c83d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3c83d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3c83d-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="3c83d-110">Called by:</span></span>  <br/> |<span data-ttu-id="3c83d-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="3c83d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPMALLOC MAPIGetDefaultMalloc( );
```

## <a name="parameters"></a><span data-ttu-id="3c83d-112">参数</span><span class="sxs-lookup"><span data-stu-id="3c83d-112">Parameters</span></span>

<span data-ttu-id="3c83d-113">无。</span><span class="sxs-lookup"><span data-stu-id="3c83d-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="3c83d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="3c83d-114">Return value</span></span>

<span data-ttu-id="3c83d-115">**MAPIGetDefaultMalloc**函数返回指向默认 MAPI 内存分配函数的指针。</span><span class="sxs-lookup"><span data-stu-id="3c83d-115">The **MAPIGetDefaultMalloc** function returns a pointer to the default MAPI memory allocation function.</span></span> 
  

