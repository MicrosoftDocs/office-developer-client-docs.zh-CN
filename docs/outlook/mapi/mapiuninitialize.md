---
title: MAPIUninitialize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIUninitialize
api_type:
- HeaderDef
ms.assetid: 0f4e54dc-80e5-49a7-9703-0225d8133492
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c1a78889ea98133af46089fdc93b0c1c4bb24226
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776415"
---
# <a name="mapiuninitialize"></a><span data-ttu-id="57693-103">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="57693-103">MAPIUninitialize</span></span>

  
  
<span data-ttu-id="57693-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="57693-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="57693-105">减少引用计数，清理，并删除每个实例全局数据的 MAPI DLL。</span><span class="sxs-lookup"><span data-stu-id="57693-105">Decrements the reference count, cleans up, and deletes per-instance global data for the MAPI DLL.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57693-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="57693-106">Header file:</span></span>  <br/> |<span data-ttu-id="57693-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="57693-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="57693-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="57693-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="57693-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="57693-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="57693-110">调用：</span><span class="sxs-lookup"><span data-stu-id="57693-110">Called by:</span></span>  <br/> |<span data-ttu-id="57693-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="57693-111">Client applications</span></span>  <br/> |
   
```cpp
void MAPIUninitialize ( void );
```

## <a name="parameters"></a><span data-ttu-id="57693-112">参数</span><span class="sxs-lookup"><span data-stu-id="57693-112">Parameters</span></span>

<span data-ttu-id="57693-113">无</span><span class="sxs-lookup"><span data-stu-id="57693-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="57693-114">返回值</span><span class="sxs-lookup"><span data-stu-id="57693-114">Return value</span></span>

<span data-ttu-id="57693-115">无。</span><span class="sxs-lookup"><span data-stu-id="57693-115">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="57693-116">备注</span><span class="sxs-lookup"><span data-stu-id="57693-116">Remarks</span></span>

<span data-ttu-id="57693-117">客户端应用程序调用**MAPIUninitialize**函数结束与 MAPI，与调用[MAPIInitialize](mapiinitialize.md)函数开始与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="57693-117">A client application calls the **MAPIUninitialize** function to end its interaction with MAPI, begun with a call to the [MAPIInitialize](mapiinitialize.md) function.</span></span> <span data-ttu-id="57693-118">调用**MAPIUninitialize**后，可以由客户端不进行任何其他 MAPI 呼叫。</span><span class="sxs-lookup"><span data-stu-id="57693-118">After **MAPIUninitialize** is called, no other MAPI calls can be made by the client.</span></span> 
  
 <span data-ttu-id="57693-119">**MAPIUninitialize**减少引用计数，并相应**MAPIInitialize**函数增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="57693-119">**MAPIUninitialize** decrements the reference count, and the corresponding **MAPIInitialize** function increments the reference count.</span></span> <span data-ttu-id="57693-120">因此，一个函数调用次数必须等于到其他呼叫的数目。</span><span class="sxs-lookup"><span data-stu-id="57693-120">Thus, the number of calls to one function must equal the number of calls to the other.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57693-121">不能调用**MAPIInitialize**或从**MAPIUninitialize** Win32 **DllMain**函数或创建或终止线程的任何其他函数中。</span><span class="sxs-lookup"><span data-stu-id="57693-121">You cannot call **MAPIInitialize** or **MAPIUninitialize** from within a Win32 **DllMain** function or any other function that creates or terminates threads.</span></span> <span data-ttu-id="57693-122">有关详细信息，请参阅[使用线程安全对象](using-thread-safe-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="57693-122">For more information, see [Using Thread-Safe Objects](using-thread-safe-objects.md).</span></span> 
  

