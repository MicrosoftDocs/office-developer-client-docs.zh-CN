---
title: 使用 MAPI 崩溃恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1a9871c2-b9bb-332e-b67e-85c50f7f685c
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 41d70c2ab94712e40de9011bc752c79d8c859161
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595179"
---
# <a name="use-the-mapi-crash-recovery-api"></a><span data-ttu-id="e8425-103">使用 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="e8425-103">Use the MAPI Crash Recovery API</span></span>

<span data-ttu-id="e8425-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8425-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8425-105">本主题包含演示如何从[UnhandledExceptionFilter](http://msdn.microsoft.com/en-us/library/ms681401%28VS.85%29.aspx)函数调用[MAPICrashRecovery](mapicrashrecovery.md)函数的 c + + 中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="e8425-105">This topic contains a code sample in C++ that shows how to call the [MAPICrashRecovery](mapicrashrecovery.md) function from the [UnhandledExceptionFilter](http://msdn.microsoft.com/en-us/library/ms681401%28VS.85%29.aspx) function.</span></span> <span data-ttu-id="e8425-106">[MAPICrashRecovery](mapicrashrecovery.md)函数检查个人文件夹文件 (PST) 或脱机文件夹 (OST) 文件的状态共享内存。</span><span class="sxs-lookup"><span data-stu-id="e8425-106">The [MAPICrashRecovery](mapicrashrecovery.md) function checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory.</span></span> 

<span data-ttu-id="e8425-107">如果内存处于一致状态， [MAPICrashRecovery](mapicrashrecovery.md)函数会将数据移到磁盘，并防止进一步读取或写入访问，直到终止的进程。</span><span class="sxs-lookup"><span data-stu-id="e8425-107">If the memory is in a consistent state, the [MAPICrashRecovery](mapicrashrecovery.md) function moves the data to disk and prevents further read or write access until the process is terminated.</span></span> <span data-ttu-id="e8425-108">通过确保 Pst 或 Ost 处于一致状态终止过程之前，您可以禁止 Microsoft Outlook 2010 或 Microsoft Outlook 2013 显示以下错误消息，并避免性能问题：</span><span class="sxs-lookup"><span data-stu-id="e8425-108">By ensuring that the PSTs or OSTs are in a consistent state before the process is terminated, you can prevent Microsoft Outlook 2010 or Microsoft Outlook 2013 from displaying the following error message and avoid performance problems:</span></span> 
  
<span data-ttu-id="e8425-109">**数据文件未无法正确关闭问题上次用，并且正在签。正在检查时，可能会影响性能。**</span><span class="sxs-lookup"><span data-stu-id="e8425-109">**A data file did not close properly the last time it was used and is being checked for problems. Performance might be affected while the check is in progress.**</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="e8425-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8425-110">See also</span></span>

- [<span data-ttu-id="e8425-111">关于 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="e8425-111">About the MAPI Crash Recovery API</span></span>](about-the-mapi-crash-recovery-api.md) 
- [<span data-ttu-id="e8425-112">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="e8425-112">MAPICrashRecovery</span></span>](mapicrashrecovery.md)

