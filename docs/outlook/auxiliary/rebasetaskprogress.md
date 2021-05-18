---
title: RebaseTaskProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8b8368d2-b04b-42a5-fdc3-955fc873c2f5
description: 报告约会的枚举和重定义值的进度。
ms.openlocfilehash: e5df0cd6df10ab86b1a125b9807637438976726f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326451"
---
# <a name="rebasetaskprogress"></a>RebaseTaskProgress

报告约会的枚举和重定义值的进度。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标头文件：  <br/> |tzmovelib.h  <br/> |
|实现者：  <br/> |MAPI 客户端应用程序  <br/> |
|调用者：  <br/> |Outlook重做对象  <br/> |
|指针类型：  <br/> |tzmovelib.h 中定义的 **PFNREBASETASKPROGRESS**  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskProgress(  
    ULONG ulMin, 
    ULONG ulMax, 
    ULONG ulCur, 
    REBASE_APPT_STATE State, 
    const SRow* pRowCur); 

```

## <a name="parameters"></a>参数

_ulMin_
  
> [in]正在处理的约会范围的低端。 通常为零。
    
_ulMax_
  
> [in]正在处理的约会范围的较高端。 通常是正在处理的日历文件夹中的项目数。
    
_ulCur_
  
> [in]当前正在处理的项目。
    
_State_
  
> [in]一个值，指示正在处理的项目的状态。 枚举 **REBASE_APPT_STATE** tzmovelib.h 中定义。  _State_ 是以下值之一： 
    
   - **REBASE_APPT_STATE_SCANNING_EXAMINING** — 扫描和检查项目。 
    
   - **REBASE_APPT_STATE_SCANNING_FOUND** — 扫描并找到项目。 
    
   - **REBASE_APPT_STATE_BEGIN** — 修复和启动项目。 
    
   - **REBASE_APPT_STATE_REBASING** — 固定和调整项目。 
    
   - **REBASE_APPT_STATE_SENDING** — 修复和发送会议更新。 
    
   - **REBASE_APPT_STATE_DONE** — 修复项目并完成。 
    
_pRowCur_
  
> [in]指向描述正在扫描或修复的项目的 **[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

使用 [IOlkApptRebaser](iolkapptrebaser.md) 接口的 MAPI 客户端应用程序实现此函数以跟踪项目处理。 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

