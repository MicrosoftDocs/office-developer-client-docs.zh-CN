---
title: RebaseTaskProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8b8368d2-b04b-42a5-fdc3-955fc873c2f5
description: 报告进度枚举和定位的约会。
ms.openlocfilehash: 4219ab1d59b596bebbe3ced03651716b04b51f81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774454"
---
# <a name="rebasetaskprogress"></a>RebaseTaskProgress

报告进度枚举和定位的约会。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|头文件：  <br/> |tzmovelib.h  <br/> |
|通过实现：  <br/> |MAPI 客户端应用程序  <br/> |
|调用：  <br/> |Outlook 调整对象  <br/> |
|指针类型：  <br/> |**PFNREBASETASKPROGRESS** tzmovelib.h 中定义  <br/> |
   
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
  
> [in]正在处理的约会的区域的低末尾。 通常为零。
    
_ulMax_
  
> [in]正在处理的约会的区域的高末尾。 它通常是正在处理的日历文件夹中的项目数。
    
_ulCur_
  
> [in]正在处理的当前项目。
    
_State_
  
> [in]一个值，指示正在处理的项目的状态。 枚举**REBASE_APPT_STATE** tzmovelib.h 中定义。  _状态_是以下值之一： 
    
   - **REBASE_APPT_STATE_SCANNING_EXAMINING** — 扫描和检查项目。 
    
   - **REBASE_APPT_STATE_SCANNING_FOUND** — 扫描和发现项目。 
    
   - **REBASE_APPT_STATE_BEGIN** — 正在修复和启动项目。 
    
   - **REBASE_APPT_STATE_REBASING** — 正在修复和调整项目。 
    
   - **REBASE_APPT_STATE_SENDING** — 正在修复和发送会议更新。 
    
   - **REBASE_APPT_STATE_DONE** — 解决并与项目完成。 
    
_pRowCur_
  
> [in]指向描述所扫描或修复的项的**[SRow](http://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

MAPI 客户端应用程序使用[IOlkApptRebaser](iolkapptrebaser.md)接口实现此函数来跟踪项目处理。 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

