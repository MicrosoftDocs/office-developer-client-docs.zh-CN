---
title: RebaseTaskComplete
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2de5c77c-3fac-cfb6-3719-68df4013cf11
description: 报告完成定位的约会。
ms.openlocfilehash: 9fab0d06bf0b9856b9a968f5c0db1bb15b0fe0bd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388915"
---
# <a name="rebasetaskcomplete"></a>RebaseTaskComplete

报告完成定位的约会。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标头文件：  <br/> |tzmovelib.h  <br/> |
|实现者：  <br/> |MAPI 客户端应用程序  <br/> |
|调用者：  <br/> |Outlook 调整对象  <br/> |
|指针类型：  <br/> |**PFNREBASETASKCOMPLETE** tzmovelib.h 中定义  <br/> |
   
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
  
> [in]已处理的行。 此索引引用传递到[IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md) **[SRowSet](https://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx)** 结构。
    
_pRowCur_
  
> 输入] 指向**[SRow](https://msdn.microsoft.com/library/369c2d5c-8c2b-4314-9cb2-aaa89580aa2b%28Office.15%29.aspx)** 结构的描述所处理的项。 
    
_hrResult_
  
> [in]**HRESULT**指示调整操作的结果。 
    
_fModified_
  
> [in]指定项目是否已修改。
    
_fSentUpdate_
  
> [in]指定会议是否更新消息发送。 
    
_pError_
  
> [in]指向与扩展的错误信息**MAPIERROR**结构的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

MAPI 客户端应用程序使用[IOlkApptRebaser](iolkapptrebaser.md)接口实现跟踪项目更新完成此函数。 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

