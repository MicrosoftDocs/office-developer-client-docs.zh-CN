---
title: DeinitMapiUtil
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- DeinitMapiUtil
api_type:
- HeaderDef
ms.assetid: e0b8dc9c-cc46-4d27-9497-7a55a0bfdff5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae6f7d7066638ef1b149d3e411443384d531184d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774751"
---
# <a name="deinitmapiutil"></a><span data-ttu-id="234e0-103">DeinitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="234e0-103">DeinitMapiUtil</span></span>

  
  
<span data-ttu-id="234e0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="234e0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="234e0-105">释放由[ScInitMapiUtil](scinitmapiutil.md)函数或隐式[MAPIInitialize](mapiinitialize.md)函数显式调用的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="234e0-105">Releases utility functions called explicitly by the [ScInitMapiUtil](scinitmapiutil.md) function or implicitly by the [MAPIInitialize](mapiinitialize.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="234e0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="234e0-106">Header file:</span></span>  <br/> |<span data-ttu-id="234e0-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="234e0-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="234e0-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="234e0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="234e0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="234e0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="234e0-110">调用：</span><span class="sxs-lookup"><span data-stu-id="234e0-110">Called by:</span></span>  <br/> |<span data-ttu-id="234e0-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="234e0-111">Client applications</span></span>  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a><span data-ttu-id="234e0-112">参数</span><span class="sxs-lookup"><span data-stu-id="234e0-112">Parameters</span></span>

<span data-ttu-id="234e0-113">无</span><span class="sxs-lookup"><span data-stu-id="234e0-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="234e0-114">返回值</span><span class="sxs-lookup"><span data-stu-id="234e0-114">Return value</span></span>

<span data-ttu-id="234e0-115">无</span><span class="sxs-lookup"><span data-stu-id="234e0-115">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="234e0-116">说明</span><span class="sxs-lookup"><span data-stu-id="234e0-116">Remarks</span></span>

<span data-ttu-id="234e0-117">初始化与[ScInitMapiUtil](scinitmapiutil.md)或[MAPIInitialize](mapiinitialize.md) **DeinitMapiUtil**函数版本函数。</span><span class="sxs-lookup"><span data-stu-id="234e0-117">The **DeinitMapiUtil** function release functions initialized with [ScInitMapiUtil](scinitmapiutil.md) or [MAPIInitialize](mapiinitialize.md).</span></span> 
  
<span data-ttu-id="234e0-118">使用由**ScInitMapiUtil**调用的函数完成后， **DeinitMapiUtil**必须明确调用其发布。</span><span class="sxs-lookup"><span data-stu-id="234e0-118">When use of the functions called by **ScInitMapiUtil** is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="234e0-119">相比之下， [MAPIUninitialize](mapiuninitialize.md)隐式调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="234e0-119">In contrast, [MAPIUninitialize](mapiuninitialize.md) implicitly calls **DeinitMapiUtil**.</span></span> 
  

