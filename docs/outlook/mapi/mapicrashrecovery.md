---
title: MAPICrashRecovery
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPICrashRecovery
api_type:
- COM
ms.assetid: 4172e2d3-6343-385b-c691-a64c1e198051
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 22f17df9347b4744dfe6598e7007469ffb9e5251
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776389"
---
# <a name="mapicrashrecovery"></a><span data-ttu-id="ee9f9-103">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="ee9f9-103">MAPICrashRecovery</span></span>

<span data-ttu-id="ee9f9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ee9f9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ee9f9-105">**MAPICrashRecovery**函数检查个人文件夹文件 (PST) 或脱机文件夹 (OST) 文件的状态共享内存。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-105">The **MAPICrashRecovery** function checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory.</span></span> <span data-ttu-id="ee9f9-106">如果内存处于一致状态， **MAPICrashRecovery**函数会将数据移到磁盘，并防止进一步读取或写入访问，直到终止的进程。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-106">If the memory is in a consistent state, the **MAPICrashRecovery** function moves the data to disk and prevents further read or write access until the process is terminated.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="ee9f9-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="ee9f9-107">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ee9f9-108">导出：</span><span class="sxs-lookup"><span data-stu-id="ee9f9-108">Exported by:</span></span>  <br/> |<span data-ttu-id="ee9f9-109">olmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="ee9f9-109">olmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="ee9f9-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ee9f9-110">Called by:</span></span>  <br/> |<span data-ttu-id="ee9f9-111">客户端</span><span class="sxs-lookup"><span data-stu-id="ee9f9-111">Client</span></span>  <br/> |
|<span data-ttu-id="ee9f9-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ee9f9-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="ee9f9-113">Outlook</span><span class="sxs-lookup"><span data-stu-id="ee9f9-113">Outlook</span></span>  <br/> |
   
```cpp
void MAPICrashRecovery(ULONG ulFlags);
```

## <a name="parameters"></a><span data-ttu-id="ee9f9-114">参数</span><span class="sxs-lookup"><span data-stu-id="ee9f9-114">Parameters</span></span>

<span data-ttu-id="ee9f9-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ee9f9-115">_ulFlags_</span></span>
  
> <span data-ttu-id="ee9f9-116">[in]用于控制如何执行 MAPI 故障恢复的标志。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-116">[in] Flags used to control how the MAPI crash recovery is performed.</span></span> <span data-ttu-id="ee9f9-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ee9f9-117">The following flags can be set:</span></span>
    
   - <span data-ttu-id="ee9f9-118">**MAPICRASH\_恢复**: Pst 或 Ost 处于一致状态，如果移动到磁盘，然后锁定 Pst 或 Ost 以防止读取或写入访问的数据。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-118">**MAPICRASH\_RECOVER**: If the PSTs or OSTs are in a consistent state, move the data to disk and lock the PSTs or OSTs to prevent read or write access.</span></span>
    
   - <span data-ttu-id="ee9f9-119">**MAPICRASH\_继续**： 解锁的 Pst 或 Ost 进行调试。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-119">**MAPICRASH\_CONTINUE**: Unlock the PSTs or OSTs for debugging.</span></span> <span data-ttu-id="ee9f9-120">成功调用后**MAPICrashRecovery**到与**MAPICRASH_RECOVER**标志，呼叫与**MAPICrashRecovery** **MAPICRASH\_继续**标志以允许调试继续。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-120">After a successful call to **MAPICrashRecovery** with the **MAPICRASH_RECOVER** flag, call **MAPICrashRecovery** with the **MAPICRASH\_CONTINUE** flag to allow debugging to continue.</span></span> 
    
   - <span data-ttu-id="ee9f9-121">**MAPICRASH\_SYSTEM_SHUTDOWN**: Pst 或 Ost 处于一致状态，如果移动到磁盘，然后锁定 Pst 或 Ost 以防止读取或写入访问的数据。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-121">**MAPICRASH\_SYSTEM_SHUTDOWN**: If the PSTs or OSTs are in a consistent state, move the data to disk and lock the PSTs or OSTs to prevent read or write access.</span></span> <span data-ttu-id="ee9f9-122">无法使用解除锁定 Pst 或 Ost **MAPICRASH\_继续**。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-122">The PSTs or OSTs cannot be unlocked using **MAPICRASH\_CONTINUE**.</span></span> <span data-ttu-id="ee9f9-123">必须与结合使用**MAPICRASH\_恢复**。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-123">Must be used in combination with **MAPICRASH\_RECOVER**.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ee9f9-124">说明</span><span class="sxs-lookup"><span data-stu-id="ee9f9-124">Remarks</span></span>

<span data-ttu-id="ee9f9-125">右上字节 (0xFF000000) 以供提供程序特定的崩溃恢复标志。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-125">The upper byte (0xFF000000) is reserved for provider specific crash recovery flags.</span></span>
  
<span data-ttu-id="ee9f9-126">调用与**MAPICrashRecovery** **MAPICRASH\_恢复**和响应**WM_ENDSESSION**消息**MAPICRASH_SYSTEM_SHUTDOWN**标志。</span><span class="sxs-lookup"><span data-stu-id="ee9f9-126">Call **MAPICrashRecovery** with the **MAPICRASH\_RECOVER** and **MAPICRASH_SYSTEM_SHUTDOWN** flags in response to the **WM_ENDSESSION** message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee9f9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee9f9-127">See also</span></span>

- [<span data-ttu-id="ee9f9-128">关于 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="ee9f9-128">About the MAPI Crash Recovery API</span></span>](about-the-mapi-crash-recovery-api.md)
- [<span data-ttu-id="ee9f9-129">使用 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="ee9f9-129">Use the MAPI Crash Recovery API</span></span>](how-to-use-the-mapi-crash-recovery-api.md)

