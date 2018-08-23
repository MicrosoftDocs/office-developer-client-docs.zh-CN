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
ms.openlocfilehash: e84dbc0976f5c438a7e0b5fd7cddcbf1c0659f40
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574795"
---
# <a name="deinitmapiutil"></a><span data-ttu-id="9fd1b-103">DeinitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="9fd1b-103">DeinitMapiUtil</span></span>

  
  
<span data-ttu-id="9fd1b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9fd1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9fd1b-105">释放由[ScInitMapiUtil](scinitmapiutil.md)函数或隐式[MAPIInitialize](mapiinitialize.md)函数显式调用的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="9fd1b-105">Releases utility functions called explicitly by the [ScInitMapiUtil](scinitmapiutil.md) function or implicitly by the [MAPIInitialize](mapiinitialize.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9fd1b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9fd1b-106">Header file:</span></span>  <br/> |<span data-ttu-id="9fd1b-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="9fd1b-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="9fd1b-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="9fd1b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9fd1b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9fd1b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9fd1b-110">调用：</span><span class="sxs-lookup"><span data-stu-id="9fd1b-110">Called by:</span></span>  <br/> |<span data-ttu-id="9fd1b-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="9fd1b-111">Client applications</span></span>  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a><span data-ttu-id="9fd1b-112">参数</span><span class="sxs-lookup"><span data-stu-id="9fd1b-112">Parameters</span></span>

<span data-ttu-id="9fd1b-113">无</span><span class="sxs-lookup"><span data-stu-id="9fd1b-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="9fd1b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="9fd1b-114">Return value</span></span>

<span data-ttu-id="9fd1b-115">无</span><span class="sxs-lookup"><span data-stu-id="9fd1b-115">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9fd1b-116">注解</span><span class="sxs-lookup"><span data-stu-id="9fd1b-116">Remarks</span></span>

<span data-ttu-id="9fd1b-117">初始化与[ScInitMapiUtil](scinitmapiutil.md)或[MAPIInitialize](mapiinitialize.md) **DeinitMapiUtil**函数版本函数。</span><span class="sxs-lookup"><span data-stu-id="9fd1b-117">The **DeinitMapiUtil** function release functions initialized with [ScInitMapiUtil](scinitmapiutil.md) or [MAPIInitialize](mapiinitialize.md).</span></span> 
  
<span data-ttu-id="9fd1b-118">使用由**ScInitMapiUtil**调用的函数完成后， **DeinitMapiUtil**必须明确调用其发布。</span><span class="sxs-lookup"><span data-stu-id="9fd1b-118">When use of the functions called by **ScInitMapiUtil** is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="9fd1b-119">相比之下， [MAPIUninitialize](mapiuninitialize.md)隐式调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="9fd1b-119">In contrast, [MAPIUninitialize](mapiuninitialize.md) implicitly calls **DeinitMapiUtil**.</span></span> 
  

