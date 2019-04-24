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
  
本主题包含 c + + 中的代码示例, 该示例演示如何从[UnhandledExceptionFilter](https://msdn.microsoft.com/library/ms681401%28VS.85%29.aspx)函数调用[MAPICrashRecovery](mapicrashrecovery.md)函数。 [MAPICrashRecovery](mapicrashrecovery.md)函数检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态。 

如果内存处于 "一致" 状态, 则[MAPICrashRecovery](mapicrashrecovery.md)函数会将数据移动到磁盘, 并在进程终止之前阻止更多的读取或写入访问。 通过确保 pst 或 OSTs 在进程终止之前处于一致状态, 您可以阻止 microsoft outlook 2010 或 microsoft outlook 2013 显示以下错误消息并避免性能问题: 
  
**上次使用数据文件时, 它未正确关闭, 且正在检查是否存在问题。在检查过程中, 性能可能会受到影响。**
  
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

