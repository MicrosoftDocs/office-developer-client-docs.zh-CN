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
# <a name="mapicrashrecovery"></a>MAPICrashRecovery

**适用于**：Outlook 2013 | Outlook 2016 
  
**MAPICrashRecovery** 函数检查 OST 中个人文件夹文件 (PST) 或脱机文件夹 (共享) 的状态。 如果内存状态一致 **，MAPICrashRecovery** 函数会将数据移动到磁盘，并阻止进一步读取或写入访问，直到进程终止。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |olmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
void MAPICrashRecovery(ULONG ulFlags);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]用于控制 MAPI 崩溃恢复执行方式的标志。 可以设置以下标志：
    
   - **MAPICRASH \_恢复**：如果 PST 或 OST 状态一致，将数据移动到磁盘并锁定 PST 或 TS 以防止读取或写入访问。
    
   - **MAPICRASH \_CONTINUE**：解锁用于调试的 PST 或 OST。 成功调用带 **MAPICRASH_RECOVER** 标志的 **MAPICrashRecovery** 后，使用 **MAPICRASH \_ CONTINUE** 标志调用 **MAPICrashRecovery** 以允许继续调试。 
    
   - **MAPICRASH \_SYSTEM_SHUTDOWN：** 如果TS 或 OST 状态一致，将数据移动到磁盘并锁定TS 或 OST 以防止读取或写入访问。 无法使用 MAPICRASH CONTINUE 解锁 PST **或 \_ OST。** 必须与 **MAPICRASH \_ RECOVER 结合使用**。 
    
## <a name="remarks"></a>备注

为提供程序特定的 (0xFF000000) 保留上字节标记。
  
使用 **MAPICRASH \_ RECOVER** 和 MAPICRASH_SYSTEM_SHUTDOWN 标志调用 **MAPICrashRecovery** 以响应 **WM_ENDSESSION消息。** 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 故障恢复 API](about-the-mapi-crash-recovery-api.md)
- [使用 MAPI 故障恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

