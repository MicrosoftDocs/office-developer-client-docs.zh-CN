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
ms.openlocfilehash: cb0630ba30f8d3d7ae38c165c5da60bbc12077c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592330"
---
# <a name="mapigetdefaultmalloc"></a><span data-ttu-id="269ca-103">MAPIGetDefaultMalloc</span><span class="sxs-lookup"><span data-stu-id="269ca-103">MAPIGetDefaultMalloc</span></span>

  
  
<span data-ttu-id="269ca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="269ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="269ca-105">检索默认 MAPI 内存分配函数的地址。</span><span class="sxs-lookup"><span data-stu-id="269ca-105">Retrieves the address of the default MAPI memory allocation function.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="269ca-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="269ca-106">Header file:</span></span>  <br/> |<span data-ttu-id="269ca-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="269ca-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="269ca-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="269ca-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="269ca-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="269ca-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="269ca-110">调用：</span><span class="sxs-lookup"><span data-stu-id="269ca-110">Called by:</span></span>  <br/> |<span data-ttu-id="269ca-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="269ca-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPMALLOC MAPIGetDefaultMalloc( );
```

## <a name="parameters"></a><span data-ttu-id="269ca-112">参数</span><span class="sxs-lookup"><span data-stu-id="269ca-112">Parameters</span></span>

<span data-ttu-id="269ca-113">无。</span><span class="sxs-lookup"><span data-stu-id="269ca-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="269ca-114">返回值</span><span class="sxs-lookup"><span data-stu-id="269ca-114">Return value</span></span>

<span data-ttu-id="269ca-115">**MAPIGetDefaultMalloc**函数对默认 MAPI 内存分配函数返回的指针。</span><span class="sxs-lookup"><span data-stu-id="269ca-115">The **MAPIGetDefaultMalloc** function returns a pointer to the default MAPI memory allocation function.</span></span> 
  

