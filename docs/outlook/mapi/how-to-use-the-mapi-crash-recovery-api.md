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
# <a name="use-the-mapi-crash-recovery-api"></a>使用 MAPI 故障恢复 API

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含一个 C++ 代码示例，演示如何从[UnhandledExceptionFilter](https://msdn.microsoft.com/library/ms681401%28VS.85%29.aspx)函数调用[MAPICrashRecovery](mapicrashrecovery.md)函数。 [MAPICrashRecovery](mapicrashrecovery.md)函数检查 OST 中个人文件夹文件 (PST) 或脱机文件夹 (共享) 的状态。 

如果内存状态一致 [，MAPICrashRecovery](mapicrashrecovery.md) 函数会将数据移动到磁盘，并阻止进一步读取或写入访问，直到进程终止。 通过确保在终止进程之前，TS 或 OST 的状态一致，可以防止 Microsoft Outlook 2010 或 Microsoft Outlook 2013 显示以下错误消息，并避免性能问题： 
  
**上次使用数据文件时未正确关闭，并且正在检查是否出现问题。正在进行检查时，性能可能会受到影响。**
  
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

## <a name="see-also"></a>另请参阅

- [关于 MAPI 故障恢复 API](about-the-mapi-crash-recovery-api.md) 
- [MAPICrashRecovery](mapicrashrecovery.md)

