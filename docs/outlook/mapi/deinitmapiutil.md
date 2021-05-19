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
ms.openlocfilehash: a9654efc34280941cdbc727bce9912a0a39d0fb9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427344"
---
# <a name="deinitmapiutil"></a><span data-ttu-id="defda-103">DeinitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="defda-103">DeinitMapiUtil</span></span>

  
  
<span data-ttu-id="defda-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="defda-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="defda-105">释放由 [ScInitMapiUtil](scinitmapiutil.md) 函数显式调用或 [由 MAPIInitialize 函数隐式调用的实用程序](mapiinitialize.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="defda-105">Releases utility functions called explicitly by the [ScInitMapiUtil](scinitmapiutil.md) function or implicitly by the [MAPIInitialize](mapiinitialize.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="defda-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="defda-106">Header file:</span></span>  <br/> |<span data-ttu-id="defda-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="defda-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="defda-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="defda-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="defda-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="defda-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="defda-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="defda-110">Called by:</span></span>  <br/> |<span data-ttu-id="defda-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="defda-111">Client applications</span></span>  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a><span data-ttu-id="defda-112">参数</span><span class="sxs-lookup"><span data-stu-id="defda-112">Parameters</span></span>

<span data-ttu-id="defda-113">无</span><span class="sxs-lookup"><span data-stu-id="defda-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="defda-114">返回值</span><span class="sxs-lookup"><span data-stu-id="defda-114">Return value</span></span>

<span data-ttu-id="defda-115">无</span><span class="sxs-lookup"><span data-stu-id="defda-115">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="defda-116">备注</span><span class="sxs-lookup"><span data-stu-id="defda-116">Remarks</span></span>

<span data-ttu-id="defda-117">**DeinitMapiUtil** 函数发布函数使用 [ScInitMapiUtil](scinitmapiutil.md)或 [MAPIInitialize 初始化](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="defda-117">The **DeinitMapiUtil** function release functions initialized with [ScInitMapiUtil](scinitmapiutil.md) or [MAPIInitialize](mapiinitialize.md).</span></span> 
  
<span data-ttu-id="defda-118">使用由 **ScInitMapiUtil** 调用的函数完成后，必须显式调用 **DeinitMapiUtil** 以释放它们。</span><span class="sxs-lookup"><span data-stu-id="defda-118">When use of the functions called by **ScInitMapiUtil** is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="defda-119">相比之下 [，MAPIUninitialize 隐式](mapiuninitialize.md) 调用 **DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="defda-119">In contrast, [MAPIUninitialize](mapiuninitialize.md) implicitly calls **DeinitMapiUtil**.</span></span> 
  

