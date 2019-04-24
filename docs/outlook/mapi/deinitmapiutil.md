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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336839"
---
# <a name="deinitmapiutil"></a><span data-ttu-id="f1881-103">DeinitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="f1881-103">DeinitMapiUtil</span></span>

  
  
<span data-ttu-id="f1881-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1881-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1881-105">释放由[ScInitMapiUtil](scinitmapiutil.md)函数显式或由[MAPIInitialize](mapiinitialize.md)函数隐式调用的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="f1881-105">Releases utility functions called explicitly by the [ScInitMapiUtil](scinitmapiutil.md) function or implicitly by the [MAPIInitialize](mapiinitialize.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f1881-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f1881-106">Header file:</span></span>  <br/> |<span data-ttu-id="f1881-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="f1881-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f1881-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f1881-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f1881-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f1881-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f1881-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f1881-110">Called by:</span></span>  <br/> |<span data-ttu-id="f1881-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="f1881-111">Client applications</span></span>  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a><span data-ttu-id="f1881-112">参数</span><span class="sxs-lookup"><span data-stu-id="f1881-112">Parameters</span></span>

<span data-ttu-id="f1881-113">无</span><span class="sxs-lookup"><span data-stu-id="f1881-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="f1881-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f1881-114">Return value</span></span>

<span data-ttu-id="f1881-115">无</span><span class="sxs-lookup"><span data-stu-id="f1881-115">None</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f1881-116">注解</span><span class="sxs-lookup"><span data-stu-id="f1881-116">Remarks</span></span>

<span data-ttu-id="f1881-117">**DeinitMapiUtil**函数释放使用[ScInitMapiUtil](scinitmapiutil.md)或[MAPIInitialize](mapiinitialize.md)初始化的函数。</span><span class="sxs-lookup"><span data-stu-id="f1881-117">The **DeinitMapiUtil** function release functions initialized with [ScInitMapiUtil](scinitmapiutil.md) or [MAPIInitialize](mapiinitialize.md).</span></span> 
  
<span data-ttu-id="f1881-118">在使用由**ScInitMapiUtil**调用的函数时, 必须显式调用**DeinitMapiUtil**以释放它们。</span><span class="sxs-lookup"><span data-stu-id="f1881-118">When use of the functions called by **ScInitMapiUtil** is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="f1881-119">相比之下, [MAPIUninitialize](mapiuninitialize.md)隐式调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="f1881-119">In contrast, [MAPIUninitialize](mapiuninitialize.md) implicitly calls **DeinitMapiUtil**.</span></span> 
  

