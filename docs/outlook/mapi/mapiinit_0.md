---
title: MAPIINIT_0
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIINIT_0
api_type:
- COM
ms.assetid: 70739711-ff43-407d-bc8b-6baf7a476fef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de31fe7d472b143ed8f3c108dca84a019b5ce103
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357293"
---
# <a name="mapiinit0"></a><span data-ttu-id="b7db3-103">MAPIINIT_0</span><span class="sxs-lookup"><span data-stu-id="b7db3-103">MAPIINIT_0</span></span>

  
  
<span data-ttu-id="b7db3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b7db3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b7db3-105">将选项传达给[MAPIInitialize](mapiinitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="b7db3-105">Conveys options to the [MAPIInitialize](mapiinitialize.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b7db3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b7db3-106">Header file:</span></span>  <br/> |<span data-ttu-id="b7db3-107">MAPIX。水平</span><span class="sxs-lookup"><span data-stu-id="b7db3-107">MAPIX.H</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG ulVersion;
  ULONG ulFlags;
} MAPIINIT_0, FAR *LPMAPIINIT_0;

```

## <a name="members"></a><span data-ttu-id="b7db3-108">Members</span><span class="sxs-lookup"><span data-stu-id="b7db3-108">Members</span></span>

 <span data-ttu-id="b7db3-109">**ulVersion**</span><span class="sxs-lookup"><span data-stu-id="b7db3-109">**ulVersion**</span></span>
  
> <span data-ttu-id="b7db3-110">一个整数值, 表示**MAPIINIT_0**结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="b7db3-110">An integer value that represents the version number of the **MAPIINIT_0** structure.</span></span> <span data-ttu-id="b7db3-111">**ulVersion**成员用于将来的扩展, 不代表 MAPI 接口的版本。</span><span class="sxs-lookup"><span data-stu-id="b7db3-111">The **ulVersion** member is for future expansion and does not represent the version of the MAPI interface.</span></span> <span data-ttu-id="b7db3-112">目前, **ulVersion**必须设置为 MAPI_INIT_VERSION。</span><span class="sxs-lookup"><span data-stu-id="b7db3-112">Currently, **ulVersion** must be set to MAPI_INIT_VERSION.</span></span> 
    
 <span data-ttu-id="b7db3-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="b7db3-113">**ulFlags**</span></span>
  
> <span data-ttu-id="b7db3-114">用于控制 MAPI 会话初始化的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b7db3-114">The bitmask of flags used to control the initialization of the MAPI session.</span></span> <span data-ttu-id="b7db3-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b7db3-115">The following flags can be set:</span></span>
    
<span data-ttu-id="b7db3-116">MAPI_MULTITHREAD_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="b7db3-116">MAPI_MULTITHREAD_NOTIFICATIONS</span></span> 
  
> <span data-ttu-id="b7db3-117">MAPI 应使用专用于通知处理的线程而不是第一个用于调用**MAPIInitialize**的线程生成通知。</span><span class="sxs-lookup"><span data-stu-id="b7db3-117">MAPI should generate notifications using a thread dedicated to notification handling instead of the first thread used to call **MAPIInitialize**.</span></span>
    
<span data-ttu-id="b7db3-118">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="b7db3-118">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="b7db3-119">调用方以 Windows 服务的形式运行。</span><span class="sxs-lookup"><span data-stu-id="b7db3-119">The caller is running as a Windows service.</span></span> <span data-ttu-id="b7db3-120">未作为 Windows 服务运行的调用方不应设置此标志;作为服务运行的调用方必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="b7db3-120">Callers that are not running as a Windows service should not set this flag; callers that are running as a service must set this flag.</span></span>
    
<span data-ttu-id="b7db3-121">MAPI_NO_COINIT</span><span class="sxs-lookup"><span data-stu-id="b7db3-121">MAPI_NO_COINIT</span></span>
  
> <span data-ttu-id="b7db3-122">设置 MAPI_NO_COINT 标志, 以便**MAPIInitialize**不会尝试使用[CoInitialize](https://msdn.microsoft.com/library/0f171cf4-87b9-43a6-97f2-80ed344fe376%28Office.15%29.aspx)调用来初始化 COM。</span><span class="sxs-lookup"><span data-stu-id="b7db3-122">Set the MAPI_NO_COINT flag so that **MAPIInitialize** does not try to initialize COM with a call to [CoInitialize](https://msdn.microsoft.com/library/0f171cf4-87b9-43a6-97f2-80ed344fe376%28Office.15%29.aspx).</span></span> <span data-ttu-id="b7db3-123">如果将**MAPIINIT_0**结构传递到_ulFlags_设置为 MAPI_NO_COINIT 的**MAPIInitialize**中, MAPI 将假定 COM 已初始化, 并将绕过**CoInitialize**调用。</span><span class="sxs-lookup"><span data-stu-id="b7db3-123">If a **MAPIINIT_0** structure is passed into **MAPIInitialize** with  _ulFlags_ set to MAPI_NO_COINIT, MAPI will assume that COM has already been initialized and will bypass the call to **CoInitialize**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b7db3-124">注解</span><span class="sxs-lookup"><span data-stu-id="b7db3-124">Remarks</span></span>

<span data-ttu-id="b7db3-125">多线程客户端应设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志。</span><span class="sxs-lookup"><span data-stu-id="b7db3-125">Multithreaded clients should set the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> <span data-ttu-id="b7db3-126">如果未设置标志, 则会在用于对**MAPIInitialize**的第一次调用的线程上生成通知。</span><span class="sxs-lookup"><span data-stu-id="b7db3-126">If the flag is not set, notifications are generated on the thread used to make the first call to **MAPIInitialize**.</span></span> 
  
<span data-ttu-id="b7db3-127">有关何时设置此标志以及如何在客户端中实现线程安全的详细信息, 请参阅[MAPI 中的线程处理](threading-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="b7db3-127">For more information about when to set this flag and how to implement thread safety in a client, see [Threading in MAPI](threading-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b7db3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7db3-128">See also</span></span>



[<span data-ttu-id="b7db3-129">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="b7db3-129">MAPIInitialize</span></span>](mapiinitialize.md)


[<span data-ttu-id="b7db3-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b7db3-130">MAPI Structures</span></span>](mapi-structures.md)

