---
title: HrCreateApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 265028b7-a583-f6ba-0214-5a4322f98f35
description: 初始化 IOlkApptRebaser 对象用于在 Outlook 日历中定位约会。
ms.openlocfilehash: fec0407c3f129290d03f9b26b0b3f072a229b003
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774199"
---
# <a name="hrcreateapptrebaser"></a>HrCreateApptRebaser

初始化[IOlkApptRebaser](iolkapptrebaser.md)对象用于在 Outlook 日历中定位约会。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|头文件：  <br/> |tzmovelib.h  <br/> |
|通过实现：  <br/> |tzmovelib.dll  <br/> |
|调用：  <br/> |MAPI 客户端应用程序  <br/> |
|指针类型：  <br/> |**LPHRCREATEAPPTREBASER** <br/> |
|DLL 入口点：  <br/> |**HrCreateApptRebaser@44** <br/> |
   
```cpp
HRESULT HrCreateApptRebaser(  
    ULONG ulFlags, 
    IMAPISession *pSession, 
    IMsgStore *pCalendarMsgStore, 
    IMAPIFolder *pCalendarFolder, 
    LPCWSTR pwszUpdatePrefix, 
    const FILETIME *pftInstallDateUTC, 
    LONG lExpansionDepth, 
    const TZDEFINITION *pTZTo, 
    const TZDEFINITION *pTZMissing, 
    MAPIERROR **ppError, 
    IOlkApptRebaser **ppApptRebase); 

```

## <a name="parameters"></a>参数

_ulFlags_
  
> [中]所必需。 用于控制定位的执行方式的标志位掩码。 以下标志可以设置，并在 tzmovelib.h 中定义：
    
   - **REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** — 包含用户的会议组织者的约会项目重新设定基址。 请注意，默认情况下，这会导致 Outlook 发送给所有与会者正在重新设定基址任何会议的会议更新。 您可以将此标志与**REBASE_FLAG_FORCE_NO_EX_UPDATES**或**REBASE_FLAG_FORCE_NO_UPDATES**更改如何处理会议更新。 
    
   - **REBASE_FLAG_UPDATE_UNMARKED** — 更新尚未标记的约会项目所在的时区。 如果指定此标志，则*pTZMissing*值用于中创建项目所在的时区作为没有所在的时区数据的所有项目。 
    
   - **REBASE_FLAG_UPDATE_ONLYRECURRING** — 更新仅定期约会项目。 
    
   - **REBASE_FLAG_NO_UI** — 不显示任何用户界面 (UI)，包括登录时打开的消息存储通常显示的对话框。 
    
   - **REBASE_FLAG_UPDATE_MINIMIZEAPPTS** — 不定在过去发生的约会项目。 
    
   - **REBASE_FLAG_FORCE_REBASE** — 不检查的定位决策，组织者，但定顺序用户是与会者的约会项目。 
    
   - **REBASE_FLAG_FORCE_NO_EX_UPDATES** — 发送更新仅当用户是组织者和收件人未连接到 Exchange 服务器。 
    
   - **REBASE_FLAG_FORCE_NO_UPDATES** — 从不发送更新。 
    
   - **REBASE_FLAG_ONLY_CREATED_PRE_PATCH** — 定仅应用修补程序之前创建的单实例约会项目。 
    
   - **REBASE_FLAG_REPORTING_MODE** — 执行操作不实际重定基本值，只报告的约会项目将被重新设定基址。 
    
   - **REBASE_FLAG_SEND_RESOURCE_UPDATES** — 会议更新发送到的资源。 
    
_pSession_
  
> [中]所必需。 指向 MAPI 会话接口的指针。
    
_pCalendarMsgStore_
  
> [中]所必需。 指向包含要在重新设定基址的约会项的消息存储的指针。
    
_pCalendarFolder_
  
> [中]所必需。 包含约会项目重新设定基址的日历文件夹指向的指针。
    
_pwszUpdatePrefix_
  
> [中]可选。 一个包含要预置在会议请求的前缀字符串指向的指针。 可能为 NULL。
    
_pftInstallDateUTC_
  
> [中]可选。 所在的时区修补程序安装日期。 设置了**REBASE_FLAG_ONLY_CREATED_PRE_PATCH**标志的情况下，才使用。 
    
_IExpansionDepth_
  
> [中]可选。 展开通讯组列表来排除收件人时的扩展深度连接到 Exchange 服务器。 如果设置了**REBASE_FLAG_FORCE_NO_EX_UPDATES**标志，仅使用。 
    
_pTZTo_
  
> [中]所必需。 指向描述时区重新到设定基址**TZDEFINITION**结构的指针。 **TZDEFINITION** tzmovelib 中定义。 
    
pTZMissing
  
> [中]所必需。 指向描述时区假定如果时区信息不标记的项的**TZDEFINITION**结构的指针。 不能为空，但只能使用如果设置了**REBASE_FLAG_UPDATE_UNMARKED**标志。 
    
_ppError_
  
> [输出]指向包含用于错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 可以为 NULL，如果需要未扩展的错误的信息。 释放与[MAPIFreeBuffer](http://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx)。 
    
_ppApptRebase_
  
> [输出]指向返回**IOlkApptRebaser**接口的指针的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

当使用[GetProcAddress](http://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx)查找 tzmovelib.dll 中此函数的地址，指定**HrCreateApptRebaser@44**作为过程名称。 并非所有标记都有效与每个其他结合使用。 
  
有关的各种选项的详细信息，请参阅"command-line options for Outlook 所在的时区数据更新工具词汇表"一节中的[KB 931667： 如何使用 Microsoft Office outlook 的时区数据更新工具地址时区更改](http://support.microsoft.com/kb/931667/en-us)。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

