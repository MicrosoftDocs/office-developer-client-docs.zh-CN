---
title: HrCreateApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 265028b7-a583-f6ba-0214-5a4322f98f35
description: 初始化 IOlkApptRebaser 对象，以用于对日历中的约会Outlook基。
ms.openlocfilehash: 33ad47d59ee2ca1b2461f730494f3466b9f8b54a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317610"
---
# <a name="hrcreateapptrebaser"></a>HrCreateApptRebaser

初始化[IOlkApptRebaser](iolkapptrebaser.md)对象，以用于对日历中的约会Outlook基。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标头文件：  <br/> |tzmovelib.h  <br/> |
|实现者：  <br/> |tzmovelib.dll  <br/> |
|调用者：  <br/> |MAPI 客户端应用程序  <br/> |
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
  
> [中]所必需。 用于控制如何执行重基的标记的位掩码。 可以在 tzmovelib.h 中设置和定义以下标志：
    
   - **REBASE_FLAG_UPDATE_ORGANIZED_MEETINGS** - 用户是会议组织者的约会项目将重新确定基本。 请注意，默认情况下，这将导致Outlook会议更新发送给任何重新基于会议的所有与会者。 可以将此标志与 **会议REBASE_FLAG_FORCE_NO_EX_UPDATES或****REBASE_FLAG_FORCE_NO_UPDATES更改** 会议更新的处理方式。 
    
   - **REBASE_FLAG_UPDATE_UNMARKED** - 更新尚未标记为时区的约会项目。 如果指定此标志  *，pTZMissing*  值将用作为没有时区数据的所有项目创建项目的时区。 
    
   - **REBASE_FLAG_UPDATE_ONLYRECURRING** - 仅更新定期约会项目。 
    
   - **REBASE_FLAG_NO_UI** -在 UI (不显示任何用户界面) ，包括在打开邮件存储时通常显示的登录对话框。 
    
   - **REBASE_FLAG_UPDATE_MINIMIZEAPPTS** - 不要重基于过去发生的约会项目。 
    
   - **REBASE_FLAG_FORCE_REBASE** - 不要检查组织者是否对决策进行重定基底，而应重定用户作为与会者的约会项目的基底。 
    
   - **REBASE_FLAG_FORCE_NO_EX_UPDATES** - 仅在用户是组织者且收件人未连接到邮箱时发送Exchange Server。 
    
   - **REBASE_FLAG_FORCE_NO_UPDATES** - 从不发送更新。 
    
   - **REBASE_FLAG_ONLY_CREATED_PRE_PATCH** - 仅重基于应用修补程序之前创建的单实例约会项目。 
    
   - **REBASE_FLAG_REPORTING_MODE** -实际上不要重定基本数据库，只需报告将重新基于的约会项目。 
    
   - **REBASE_FLAG_SEND_RESOURCE_UPDATES** — 将会议更新发送到资源。 
    
_pSession_
  
> [中]所必需。 指向 MAPI 会话接口的指针。
    
_pCalendarMsgStore_
  
> [中]所必需。 指向包含要重定基元的约会项目的邮件存储的指针。
    
_pCalendarFolder_
  
> [中]所必需。 指向包含要重定基元的约会项目的日历文件夹的指针。
    
_pwszUpdatePrefix_
  
> [中]可选。 指向字符串的指针，其中包含在会议请求上前面附加的前缀。 可能为 NULL。
    
_pftInstallDateUTC_
  
> [中]可选。 时区修补程序安装日期。 仅在 **设置REBASE_FLAG_ONLY_CREATED_PRE_PATCH时** 使用。 
    
_IExpansionDepth_
  
> [中]可选。 展开扩展深度列表以排除连接到通讯组列表的收件人时，Exchange Server。 仅在 **设置REBASE_FLAG_FORCE_NO_EX_UPDATES时** 使用。 
    
_pTZTo_
  
> [中]所必需。 一个指向描述要重新基于的时区的 **TZDEFINITION** 结构的指针。 **TZDEFINITION** 在 tzmovelib 中定义。 
    
pTZMissing
  
> [中]所必需。 一个指向 **TZDEFINITION** 结构的指针，该结构描述在项目上未标记时区信息时要假定的时区。 不得为 NULL，但仅在设置 REBASE_FLAG_UPDATE_UNMARKED **标志时** 使用。 
    
_ppError_
  
> [out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。 如果不需要扩展的错误信息，则可以是 NULL。 使用 [MAPIFreeBuffer 免费](https://msdn.microsoft.com/library/9412594f-8acc-4c7e-a668-4ec1da0ad9cf%28Office.15%29.aspx)。 
    
_ppApptRebase_
  
> [out]指向返回的 **IOlkApptRebaser** 接口的指针的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

使用 [GetProcAddress](https://msdn.microsoft.com/library/a0d7fc09-f888-4f46-a571-d3719a627597%28Office.15%29.aspx) 在 tzmovelib.dll 中查找此函数的地址时，HrCreateApptRebaser@44 **指定为过程** 名称。 并非所有标志都相互有效。 
  
有关各种选项的详细信息，请参阅[KB 931667](https://support.microsoft.com/kb/931667/en-us)中的"Outlook 时区数据更新工具的命令行选项词汇表"一节：如何使用 Microsoft Office Outlook 时区数据更新工具解决时区更改。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

