---
title: 关于以编程方式为夏令时变基日历
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 38b342d9-ab10-04b6-5490-9a45f847a60f
description: 在本主题中，在弹簧和秋季之间的这一时段称为 DST 时段。
ms.openlocfilehash: 8d9a0ffda89ee9d8847cde59181747588a50e947
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316952"
---
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a>关于以编程方式为夏令时变基日历

多个国家/地区都遵循夏令时 (DST) 延长时钟，以便晚上的夏时制时间更长。 这通常是通过设置弹簧中提前一小时时钟，在秋季将时钟设置回一小时。 在本主题中，在弹簧和秋季之间的这一时段称为 DST 时段。 对于 DST 的开始和结束时间，大多数国家/地区都有自己的法规。 DST 时段的日期可能会因年而变，用户必须每次 DST Outlook更改时更新其 Microsoft 日历。 
  
如果使用 Vista Windows或更高版本Windows版本，或打开 Windows 自动更新，则 DST 中的更改可能不会受到影响。 否则，应安装 DST 更新Windows。 无论更新是自动安装的，还是由 IT 部门代表您安装的，或者您自己作为主用户安装的，DST 期间发生的某些现有约会在安装 Windows 的 DST 更新后可能显示错误的时间。 定期约会和单实例约会均如此。 必须更新这些约会，以在 Outlook、Outlook Web App 以及基于协作数据对象 (CDO) 的应用程序中正确显示这些约会。 由于 DST，更新日历上显示不正确的约会称为重基于日历。
  
Outlook为用户提供工具，Exchange Server为管理员提供重基于日历的工具。 Outlook为用户提供时区数据更新Outlook工具。 使用此工具，用户可以更新自己的日历。 Exchange Server提供了 Exchange 日历更新工具，可帮助管理员避免因将 Outlook 工具广泛部署到所有用户而造成困难，并确保每个用户正确运行 Outlook 工具。
  
除了依赖用户运行时区数据更新工具或管理员来运行 Exchange 日历更新工具之外，第三方 MAPI 客户端软件开发人员还可以下载 DLL，Tzmovelib.dll。 通过使用此程序集，开发人员可以使用与日历重基Outlook和Exchange Server相同的 API。 

以下列表显示了日历重基 API：
  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)
    
- [IOlkApptRebaser](iolkapptrebaser.md)
    
- [IOlkApptRebaser::BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)
    
- [IOlkApptRebaser::BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)
    
- [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)
    
- [IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)
    
- [PidLidAppointmentTimeZoneDefinitionEndDisplay](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)
    
- [PidLidAppointmentTimeZoneDefinitionRecur](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)
    
- [PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)
    
- [PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)
    
- [RebaseTaskComplete](rebasetaskcomplete.md)
    
- [RebaseTaskProgress](rebasetaskprogress.md)
    
- [TZDEFINITION](tzdefinition.md)
    
- [TZREG](tzreg.md)
    
- [TZRULE](tzrule.md)
    
若要使用日历重基基 API 编写约会重基工具，可以使用以下过程：
  
1. 使用 **IOlkApptRebaser：：BeginEnumerateAppointments** 和 **IOlkApptRebaser：：EndEnumerateAppointments** 查找作为重基的候选约会。 如有必要，提供使用户能够决定要重定基底的约会的信息。 或者，使用 MAPI 或 Outlook 对象模型通过分析 **PidLidAppointmentTimeZoneDefinitionStartDisplay、PidLidAppointmentTimeZoneDefinitionEndDisplay** 和 **PidLidAppointmentTimeZoneDefinitionRecur** 属性来检查约会的时间和定期信息。 
    
2. 使用 **HrCreateApptRebaser、IOlkApptRebaser：：BeginRebaseAppointments** 和 **IOlkApptRebaser：：EndRebaseAppointments** 重设定约会基本值。  
    
若要获取 Tzmovelib.dll 程序集，请下载 OutlookTimeZoneMoveLibRedist.exe 可再发行组件安装程序和 Tzmovelib.h 头文件，位置为[Outlook 2010：用于](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b)重基日历的辅助参考可再发行组件安装程序和头文件。 此下载适用于 Outlook 2010 及更高版本的 Outlook。 OutlookTimeZoneMoveLibRedist.exe C：\Program Files\msExTmz Tzmovelib.dll程序集文件。 请注意，第三方日历重定数据库应用程序只能重新分发安装程序、OutlookTimeZoneMoveLibRedist.exe，并且不得将程序集、Tzmovelib.dll 或任何其他提取的组件与安装程序分开重新分发。
  
## <a name="see-also"></a>另请参阅

- [关于将 TZDEFINITION 保存到流以提交到二进制属性](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [分析二进制属性读取 TZDEFINITION 结构的流](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [分析二进制属性读取 TZREG 结构的流](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [从约会中读取时区属性](how-to-read-time-zone-properties-from-an-appointment.md)
- [夏令时帮助和支持中心](https://support.microsoft.com/gp/cp_dst)
- [如何使用日历更新工具Exchange夏令时](https://support.microsoft.com/kb/941018)
- [如何使用时区数据更新工具处理时区Microsoft Office Outlook](https://support.microsoft.com/kb/931667)

