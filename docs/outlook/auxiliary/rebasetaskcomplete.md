---
title: RebaseTaskComplete
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2de5c77c-3fac-cfb6-3719-68df4013cf11
description: 报告重定约会的完成情况。
ms.openlocfilehash: 9fab0d06bf0b9856b9a968f5c0db1bb15b0fe0bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328320"
---
# <a name="rebasetaskcomplete"></a>RebaseTaskComplete

报告重定约会的完成情况。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标头文件：  <br/> |tzmovelib。h  <br/> |
|实现者：  <br/> |MAPI 客户端应用程序  <br/> |
|调用者：  <br/> |Outlook 重定对象  <br/> |
|指针类型:  <br/> |**PFNREBASETASKCOMPLETE**中定义的 tzmovelib。h  <br/> |
   
```cpp
void STDAPICALLTYPE RebaseTaskComplete(  
    ULONG ulRowIndex, 
    const SRow* pRowCur, 
    HRESULT hrResult, 
    BOOL fModified, 
    BOOL fSentUpdate, 
    const MAPIERROR* pError); 

```

## <a name="parameters"></a>参数

_ulRowIndex_
  
> 实时已处理的行。 此索引是指传递给[IOlkApptRebaser:: BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)的**[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** 结构。
    
_pRowCur_
  
> in] 指向描述已处理的项目的**[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的指针。 
    
_hrResult_
  
> 实时一个**HRESULT** , 它指示重定操作的结果。 
    
_fModified_
  
> 实时指定是否修改项目。
    
_fSentUpdate_
  
> 实时指定是否发送了会议更新邮件。 
    
_pError_
  
> 实时指向带有扩展错误信息的**MAPIERROR**结构的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注解

使用[IOlkApptRebaser](iolkapptrebaser.md)接口的 MAPI 客户端应用程序实现此函数以跟踪项更新的完成。 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

