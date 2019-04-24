---
title: HrCreateApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 265028b7-a583-f6ba-0214-5a4322f98f35
description: 初始化 IOlkApptRebaser 对象, 以便在 Outlook 日历中的重定约会中使用。
ms.openlocfilehash: 33ad47d59ee2ca1b2461f730494f3466b9f8b54a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317610"
---
# <a name="hrcreateapptrebaser"></a>HrCreateApptRebaser

初始化[IOlkApptRebaser](iolkapptrebaser.md)对象, 以便在 Outlook 日历中的重定约会中使用。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标头文件：  <br/> |tzmovelib。h  <br/> |
|实现者：  <br/> |tzmovelib。h  <br/> |
|调用者：  <br/> |MAPI 客户端应用程序  <br/> |
|指针类型:  <br/> |**LPHRCREATEAPPTREBASER** <br/> |
|DLL 入口点:  <br/> |**HrCreateApptRebaser @ 44** <br/> |
   
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
  
> [中]所必需。 用于控制如何执行重定的标志的位掩码。 可以在 tzmovelib.h 中设置和定义以下标志:
    
   - **REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** —用户是会议组织者的约会项目是 rebased。 请注意, 默认情况下, 这会导致 Outlook 向任何正在 rebased 的会议的所有与会者发送会议更新。 您可以将此标志与**REBASE_FLAG_FORCE_NO_EX_UPDATES**或**REBASE_FLAG_FORCE_NO_UPDATES**结合使用, 以更改会议更新的处理方式。 
    
   - **REBASE_FLAG_UPDATE_UNMARKED** —更新尚未使用时区标记的约会项目。 如果指定此标志, 则将*pTZMissing*值用作为没有时区数据的所有项目创建项目的时区。 
    
   - **REBASE_FLAG_UPDATE_ONLYRECURRING** —仅更新定期约会项目。 
    
   - **REBASE_FLAG_NO_UI** —不显示任何用户界面 (UI), 包括在打开邮件存储时通常会显示的登录对话框。 
    
   - **REBASE_FLAG_UPDATE_MINIMIZEAPPTS** —不变基发生在过去的约会项。 
    
   - **REBASE_FLAG_FORCE_REBASE** —不检查组织者的重定决策, 但可变基约会项, 其中用户是与会者。 
    
   - **REBASE_FLAG_FORCE_NO_EX_UPDATES** —仅当用户是组织者且收件人未连接到 Exchange 服务器时才发送更新。 
    
   - **REBASE_FLAG_FORCE_NO_UPDATES** —从不发送更新。 
    
   - **REBASE_FLAG_ONLY_CREATED_PRE_PATCH** —仅在应用修补程序之前创建的单实例约会项目变基。 
    
   - **REBASE_FLAG_REPORTING_MODE** —实际上不会变基, 只是报告将被 rebased 的约会项目。 
    
   - **REBASE_FLAG_SEND_RESOURCE_UPDATES** —将会议更新发送到资源。 
    
_pSession_
  
> [中]所必需。 指向 MAPI 会话接口的指针。
    
_pCalendarMsgStore_
  
> [中]所必需。 指向邮件存储区的指针, 该存储区包含要 rebased 的约会项目。
    
_pCalendarFolder_
  
> [中]所必需。 指向包含要 rebased 的约会项目的 "日历" 文件夹的指针。
    
_pwszUpdatePrefix_
  
> [中]可选。 指向包含前缀的字符串的指针, 该字符串将预置在会议请求上。 可以为 NULL。
    
_pftInstallDateUTC_
  
> [中]可选。 时区修补程序安装日期。 仅在设置**REBASE_FLAG_ONLY_CREATED_PRE_PATCH**标志时使用。 
    
_IExpansionDepth_
  
> [中]可选。 扩展通讯组列表以排除连接到 Exchange Server 的收件人时的扩展深度。 仅在设置**REBASE_FLAG_FORCE_NO_EX_UPDATES**标志时使用。 
    
_pTZTo_
  
> [中]所必需。 指向描述要 rebased 的时区的**TZDEFINITION**结构的指针。 **TZDEFINITION**是在 tzmovelib.h 中定义的。 
    
pTZMissing
  
> [中]所必需。 一个指向**TZDEFINITION**结构的指针, 该结构描述在不标记某一项的时区信息时要假定的时区。 不得为 NULL, 但仅在设置了**REBASE_FLAG_UPDATE_UNMARKED**标志的情况下使用。 
    
_ppError_
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果不需要任何扩展的错误信息, 则可以为 NULL。 使用[MAPIFreeBuffer](https://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx)免费。 
    
_ppApptRebase_
  
> 排除指向返回的**IOlkApptRebaser**接口的指针的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注解

使用[GetProcAddress](https://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx)在 tzmovelib.h 中查找此函数的地址时, 请指定**HrCreateApptRebaser @ 44**作为过程名称。 并不是所有的标志相互组合。 
  
有关各种选项的详细信息, 请参阅 KB 931667 中的 "Outlook 时区数据更新工具的命令行选项的术语表" 一节[: 如何使用 Microsoft Office Outlook 的时区数据更新工具来解决时区更改](https://support.microsoft.com/kb/931667/en-us)。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

