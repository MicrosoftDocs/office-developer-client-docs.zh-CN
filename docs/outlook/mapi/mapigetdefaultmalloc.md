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
ms.openlocfilehash: b236b24c10a241dbdecc28bf2e04de5f69e989e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776359"
---
# <a name="mapigetdefaultmalloc"></a><span data-ttu-id="175df-103">MAPIGetDefaultMalloc</span><span class="sxs-lookup"><span data-stu-id="175df-103">MAPIGetDefaultMalloc</span></span>

  
  
<span data-ttu-id="175df-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="175df-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="175df-105">检索默认 MAPI 内存分配函数的地址。</span><span class="sxs-lookup"><span data-stu-id="175df-105">Retrieves the address of the default MAPI memory allocation function.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="175df-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="175df-106">Header file:</span></span>  <br/> |<span data-ttu-id="175df-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="175df-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="175df-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="175df-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="175df-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="175df-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="175df-110">调用：</span><span class="sxs-lookup"><span data-stu-id="175df-110">Called by:</span></span>  <br/> |<span data-ttu-id="175df-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="175df-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPMALLOC MAPIGetDefaultMalloc( );
```

## <a name="parameters"></a><span data-ttu-id="175df-112">参数</span><span class="sxs-lookup"><span data-stu-id="175df-112">Parameters</span></span>

<span data-ttu-id="175df-113">无。</span><span class="sxs-lookup"><span data-stu-id="175df-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="175df-114">返回值</span><span class="sxs-lookup"><span data-stu-id="175df-114">Return value</span></span>

<span data-ttu-id="175df-115">**MAPIGetDefaultMalloc**函数对默认 MAPI 内存分配函数返回的指针。</span><span class="sxs-lookup"><span data-stu-id="175df-115">The **MAPIGetDefaultMalloc** function returns a pointer to the default MAPI memory allocation function.</span></span> 
  

