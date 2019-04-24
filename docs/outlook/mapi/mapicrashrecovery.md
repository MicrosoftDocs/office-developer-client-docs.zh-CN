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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357300"
---
# <a name="mapicrashrecovery"></a>MAPICrashRecovery

**适用于**：Outlook 2013 | Outlook 2016 
  
**MAPICrashRecovery**函数检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态。 如果内存处于 "一致" 状态, 则**MAPICrashRecovery**函数会将数据移动到磁盘, 并在进程终止之前阻止更多的读取或写入访问。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者:  <br/> |olmapi32  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
void MAPICrashRecovery(ULONG ulFlags);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> 实时用于控制如何执行 MAPI 故障恢复的标志。 可以设置以下标志:
    
   - **MAPICRASH\_恢复**: 如果 pst 或 OSTs 处于一致状态, 请将数据移动到磁盘, 并锁定 pst 或 OSTs 以阻止读取或写入访问。
    
   - **MAPICRASH\_继续**: 解锁 pst 或 OSTs 以进行调试。 在使用**MAPICRASH_RECOVER**标志成功调用**MAPICrashRecovery**后, 使用**\_MAPICRASH CONTINUE**标志调用**MAPICrashRecovery** , 以允许继续进行调试。 
    
   - **MAPICRASH\_SYSTEM_SHUTDOWN**: 如果 pst 或 OSTs 处于一致状态, 请将数据移动到磁盘, 并锁定 pst 或 OSTs 以阻止读取或写入访问。 无法使用**MAPICRASH\_CONTINUE**解锁 pst 或 OSTs。 必须与**MAPICRASH\_恢复**结合使用。 
    
## <a name="remarks"></a>注解

高位字节 (0xFF000000) 是为提供程序特定的故障恢复标记保留的。
  
使用**MAPICRASH\_RECOVER**和**MAPICRASH_SYSTEM_SHUTDOWN**标记调用**MAPICrashRecovery** , 以响应**WM_ENDSESSION**邮件。 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 故障恢复 API](about-the-mapi-crash-recovery-api.md)
- [使用 MAPI 故障恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

