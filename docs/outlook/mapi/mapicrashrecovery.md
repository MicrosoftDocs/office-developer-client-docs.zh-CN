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
ms.openlocfilehash: 9efafbac55a2925e04b533e7c08388c026540dff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407212"
---
# <a name="mapicrashrecovery"></a><span data-ttu-id="197dd-103">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="197dd-103">MAPICrashRecovery</span></span>

<span data-ttu-id="197dd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="197dd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="197dd-105">**MAPICrashRecovery**函数检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态。</span><span class="sxs-lookup"><span data-stu-id="197dd-105">The **MAPICrashRecovery** function checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory.</span></span> <span data-ttu-id="197dd-106">如果内存处于 "一致" 状态, 则**MAPICrashRecovery**函数会将数据移动到磁盘, 并在进程终止之前阻止更多的读取或写入访问。</span><span class="sxs-lookup"><span data-stu-id="197dd-106">If the memory is in a consistent state, the **MAPICrashRecovery** function moves the data to disk and prevents further read or write access until the process is terminated.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="197dd-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="197dd-107">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="197dd-108">导出者:</span><span class="sxs-lookup"><span data-stu-id="197dd-108">Exported by:</span></span>  <br/> |<span data-ttu-id="197dd-109">olmapi32</span><span class="sxs-lookup"><span data-stu-id="197dd-109">olmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="197dd-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="197dd-110">Called by:</span></span>  <br/> |<span data-ttu-id="197dd-111">Client</span><span class="sxs-lookup"><span data-stu-id="197dd-111">Client</span></span>  <br/> |
|<span data-ttu-id="197dd-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="197dd-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="197dd-113">Outlook</span><span class="sxs-lookup"><span data-stu-id="197dd-113">Outlook</span></span>  <br/> |
   
```cpp
void MAPICrashRecovery(ULONG ulFlags);
```

## <a name="parameters"></a><span data-ttu-id="197dd-114">参数</span><span class="sxs-lookup"><span data-stu-id="197dd-114">Parameters</span></span>

<span data-ttu-id="197dd-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="197dd-115">_ulFlags_</span></span>
  
> <span data-ttu-id="197dd-116">实时用于控制如何执行 MAPI 故障恢复的标志。</span><span class="sxs-lookup"><span data-stu-id="197dd-116">[in] Flags used to control how the MAPI crash recovery is performed.</span></span> <span data-ttu-id="197dd-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="197dd-117">The following flags can be set:</span></span>
    
   - <span data-ttu-id="197dd-118">**MAPICRASH\_恢复**: 如果 pst 或 OSTs 处于一致状态, 请将数据移动到磁盘, 并锁定 pst 或 OSTs 以阻止读取或写入访问。</span><span class="sxs-lookup"><span data-stu-id="197dd-118">**MAPICRASH\_RECOVER**: If the PSTs or OSTs are in a consistent state, move the data to disk and lock the PSTs or OSTs to prevent read or write access.</span></span>
    
   - <span data-ttu-id="197dd-119">**MAPICRASH\_继续**: 解锁 pst 或 OSTs 以进行调试。</span><span class="sxs-lookup"><span data-stu-id="197dd-119">**MAPICRASH\_CONTINUE**: Unlock the PSTs or OSTs for debugging.</span></span> <span data-ttu-id="197dd-120">在使用**MAPICRASH_RECOVER**标志成功调用**MAPICrashRecovery**后, 使用**\_MAPICRASH CONTINUE**标志调用**MAPICrashRecovery** , 以允许继续进行调试。</span><span class="sxs-lookup"><span data-stu-id="197dd-120">After a successful call to **MAPICrashRecovery** with the **MAPICRASH_RECOVER** flag, call **MAPICrashRecovery** with the **MAPICRASH\_CONTINUE** flag to allow debugging to continue.</span></span> 
    
   - <span data-ttu-id="197dd-121">**MAPICRASH\_SYSTEM_SHUTDOWN**: 如果 pst 或 OSTs 处于一致状态, 请将数据移动到磁盘, 并锁定 pst 或 OSTs 以阻止读取或写入访问。</span><span class="sxs-lookup"><span data-stu-id="197dd-121">**MAPICRASH\_SYSTEM_SHUTDOWN**: If the PSTs or OSTs are in a consistent state, move the data to disk and lock the PSTs or OSTs to prevent read or write access.</span></span> <span data-ttu-id="197dd-122">无法使用**MAPICRASH\_CONTINUE**解锁 pst 或 OSTs。</span><span class="sxs-lookup"><span data-stu-id="197dd-122">The PSTs or OSTs cannot be unlocked using **MAPICRASH\_CONTINUE**.</span></span> <span data-ttu-id="197dd-123">必须与**MAPICRASH\_恢复**结合使用。</span><span class="sxs-lookup"><span data-stu-id="197dd-123">Must be used in combination with **MAPICRASH\_RECOVER**.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="197dd-124">说明</span><span class="sxs-lookup"><span data-stu-id="197dd-124">Remarks</span></span>

<span data-ttu-id="197dd-125">高位字节 (0xFF000000) 是为提供程序特定的故障恢复标记保留的。</span><span class="sxs-lookup"><span data-stu-id="197dd-125">The upper byte (0xFF000000) is reserved for provider specific crash recovery flags.</span></span>
  
<span data-ttu-id="197dd-126">使用**MAPICRASH\_RECOVER**和**MAPICRASH_SYSTEM_SHUTDOWN**标记调用**MAPICrashRecovery** , 以响应**WM_ENDSESSION**邮件。</span><span class="sxs-lookup"><span data-stu-id="197dd-126">Call **MAPICrashRecovery** with the **MAPICRASH\_RECOVER** and **MAPICRASH_SYSTEM_SHUTDOWN** flags in response to the **WM_ENDSESSION** message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="197dd-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="197dd-127">See also</span></span>

- [<span data-ttu-id="197dd-128">关于 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="197dd-128">About the MAPI Crash Recovery API</span></span>](about-the-mapi-crash-recovery-api.md)
- [<span data-ttu-id="197dd-129">使用 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="197dd-129">Use the MAPI Crash Recovery API</span></span>](how-to-use-the-mapi-crash-recovery-api.md)

