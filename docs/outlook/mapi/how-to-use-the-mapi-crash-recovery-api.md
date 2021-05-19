---
title: 使用 MAPI 故障恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1a9871c2-b9bb-332e-b67e-85c50f7f685c
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: a73889982e4aa72fb664a8eafd6fc8704e581e98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346422"
---
# <a name="use-the-mapi-crash-recovery-api"></a><span data-ttu-id="cca3e-103">使用 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="cca3e-103">Use the MAPI Crash Recovery API</span></span>

<span data-ttu-id="cca3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cca3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cca3e-105">本主题包含一个 C++ 代码示例，演示如何从[UnhandledExceptionFilter](https://msdn.microsoft.com/library/ms681401%28VS.85%29.aspx)函数调用[MAPICrashRecovery](mapicrashrecovery.md)函数。</span><span class="sxs-lookup"><span data-stu-id="cca3e-105">This topic contains a code sample in C++ that shows how to call the [MAPICrashRecovery](mapicrashrecovery.md) function from the [UnhandledExceptionFilter](https://msdn.microsoft.com/library/ms681401%28VS.85%29.aspx) function.</span></span> <span data-ttu-id="cca3e-106">[MAPICrashRecovery](mapicrashrecovery.md)函数检查 OST 中个人文件夹文件 (PST) 或脱机文件夹 (共享) 的状态。</span><span class="sxs-lookup"><span data-stu-id="cca3e-106">The [MAPICrashRecovery](mapicrashrecovery.md) function checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory.</span></span> 

<span data-ttu-id="cca3e-107">如果内存状态一致 [，MAPICrashRecovery](mapicrashrecovery.md) 函数会将数据移动到磁盘，并阻止进一步读取或写入访问，直到进程终止。</span><span class="sxs-lookup"><span data-stu-id="cca3e-107">If the memory is in a consistent state, the [MAPICrashRecovery](mapicrashrecovery.md) function moves the data to disk and prevents further read or write access until the process is terminated.</span></span> <span data-ttu-id="cca3e-108">通过确保在终止进程之前，TS 或 OST 的状态一致，可以防止 Microsoft Outlook 2010 或 Microsoft Outlook 2013 显示以下错误消息，并避免性能问题：</span><span class="sxs-lookup"><span data-stu-id="cca3e-108">By ensuring that the PSTs or OSTs are in a consistent state before the process is terminated, you can prevent Microsoft Outlook 2010 or Microsoft Outlook 2013 from displaying the following error message and avoid performance problems:</span></span> 
  
<span data-ttu-id="cca3e-109">**上次使用数据文件时未正确关闭，并且正在检查是否出现问题。正在进行检查时，性能可能会受到影响。**</span><span class="sxs-lookup"><span data-stu-id="cca3e-109">**A data file did not close properly the last time it was used and is being checked for problems. Performance might be affected while the check is in progress.**</span></span>
  
```cpp
LONG WINAPI UnhandledExceptionFilter(__in EXCEPTION_POINTERS* pep) 
{ 
    // Let the OS terminate the process upon return. 
    LONG retval = EXCEPTION_EXECUTE_HANDLER; 
 
    switch (pep->ExceptionRecord->ExceptionCode) 
    { 
        case EXCEPTION_BREAKPOINT: 
        case EXCEPTION_SINGLE_STEP: 
            // Ignore debugging exceptions. 
            retval = EXCEPTION_CONTINUE_SEARCH; 
            break; 
 
        default: 
            // The process is going to be terminated, so disconnect the MAPI database. 
            MAPICrashRecovery(MAPICRASH_RECOVER); 
            // Optionally, you can display a crash reporting dialog box here. 
            // If the user chooses to debug,  
            // call MAPICrashRecovery(MAPICRASH_CONTINUE). 
            break; 
    } 
 
    return retval; 
}
```

## <a name="see-also"></a><span data-ttu-id="cca3e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca3e-110">See also</span></span>

- [<span data-ttu-id="cca3e-111">关于 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="cca3e-111">About the MAPI Crash Recovery API</span></span>](about-the-mapi-crash-recovery-api.md) 
- [<span data-ttu-id="cca3e-112">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="cca3e-112">MAPICrashRecovery</span></span>](mapicrashrecovery.md)

