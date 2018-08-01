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
# <a name="mapicrashrecovery"></a>MAPICrashRecovery

**适用于**： Outlook 
  
**MAPICrashRecovery**函数检查个人文件夹文件 (PST) 或脱机文件夹 (OST) 文件的状态共享内存。 如果内存处于一致状态， **MAPICrashRecovery**函数会将数据移到磁盘，并防止进一步读取或写入访问，直到终止的进程。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |olmapi32.dll  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
```cpp
void MAPICrashRecovery(ULONG ulFlags);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]用于控制如何执行 MAPI 故障恢复的标志。 可以设置以下标志：
    
   - **MAPICRASH\_恢复**: Pst 或 Ost 处于一致状态，如果移动到磁盘，然后锁定 Pst 或 Ost 以防止读取或写入访问的数据。
    
   - **MAPICRASH\_继续**： 解锁的 Pst 或 Ost 进行调试。 成功调用后**MAPICrashRecovery**到与**MAPICRASH_RECOVER**标志，呼叫与**MAPICrashRecovery** **MAPICRASH\_继续**标志以允许调试继续。 
    
   - **MAPICRASH\_SYSTEM_SHUTDOWN**: Pst 或 Ost 处于一致状态，如果移动到磁盘，然后锁定 Pst 或 Ost 以防止读取或写入访问的数据。 无法使用解除锁定 Pst 或 Ost **MAPICRASH\_继续**。 必须与结合使用**MAPICRASH\_恢复**。 
    
## <a name="remarks"></a>说明

右上字节 (0xFF000000) 以供提供程序特定的崩溃恢复标志。
  
调用与**MAPICrashRecovery** **MAPICRASH\_恢复**和响应**WM_ENDSESSION**消息**MAPICRASH_SYSTEM_SHUTDOWN**标志。 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 崩溃恢复 API](about-the-mapi-crash-recovery-api.md)
- [使用 MAPI 崩溃恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

