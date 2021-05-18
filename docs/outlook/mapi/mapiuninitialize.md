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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f7339588bcc6815545e7341eafffe9cf001c1d76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408521"
---
# <a name="mapiuninitialize"></a><span data-ttu-id="2c9b8-103">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="2c9b8-103">MAPIUninitialize</span></span>

  
  
<span data-ttu-id="2c9b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c9b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c9b8-105">为 MAPI DLL 缩小引用计数、清理和删除每个实例的全局数据。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-105">Decrements the reference count, cleans up, and deletes per-instance global data for the MAPI DLL.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2c9b8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2c9b8-106">Header file:</span></span>  <br/> |<span data-ttu-id="2c9b8-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="2c9b8-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="2c9b8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2c9b8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2c9b8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2c9b8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2c9b8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2c9b8-110">Called by:</span></span>  <br/> |<span data-ttu-id="2c9b8-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2c9b8-111">Client applications</span></span>  <br/> |
   
```cpp
void MAPIUninitialize ( void );
```

## <a name="parameters"></a><span data-ttu-id="2c9b8-112">参数</span><span class="sxs-lookup"><span data-stu-id="2c9b8-112">Parameters</span></span>

<span data-ttu-id="2c9b8-113">无</span><span class="sxs-lookup"><span data-stu-id="2c9b8-113">None</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="2c9b8-114">返回值</span><span class="sxs-lookup"><span data-stu-id="2c9b8-114">Return value</span></span>

<span data-ttu-id="2c9b8-115">无。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-115">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2c9b8-116">说明</span><span class="sxs-lookup"><span data-stu-id="2c9b8-116">Remarks</span></span>

<span data-ttu-id="2c9b8-117">客户端应用程序调用 **MAPIUninitialize** 函数以结束其与 MAPI 的交互，从调用 [MAPIInitialize 函数开始](mapiinitialize.md) 。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-117">A client application calls the **MAPIUninitialize** function to end its interaction with MAPI, begun with a call to the [MAPIInitialize](mapiinitialize.md) function.</span></span> <span data-ttu-id="2c9b8-118">调用 **MAPIUninitialize** 后，客户端无法进行任何其他 MAPI 调用。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-118">After **MAPIUninitialize** is called, no other MAPI calls can be made by the client.</span></span> 
  
 <span data-ttu-id="2c9b8-119">**MAPIUninitialize** 会缩小引用计数，相应的 **MAPIInitialize** 函数将递增引用计数。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-119">**MAPIUninitialize** decrements the reference count, and the corresponding **MAPIInitialize** function increments the reference count.</span></span> <span data-ttu-id="2c9b8-120">因此，对一个函数的调用数必须等于对另一个函数的调用数。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-120">Thus, the number of calls to one function must equal the number of calls to the other.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2c9b8-121">不能从 Win32 **DllMain** 函数或其他创建或终止线程的函数中调用 **MAPIInitialize** 或 **MAPIUninitialize。**</span><span class="sxs-lookup"><span data-stu-id="2c9b8-121">You cannot call **MAPIInitialize** or **MAPIUninitialize** from within a Win32 **DllMain** function or any other function that creates or terminates threads.</span></span> <span data-ttu-id="2c9b8-122">有关详细信息，请参阅使用对象 [Thread-Safe对象](using-thread-safe-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9b8-122">For more information, see [Using Thread-Safe Objects](using-thread-safe-objects.md).</span></span> 
  

