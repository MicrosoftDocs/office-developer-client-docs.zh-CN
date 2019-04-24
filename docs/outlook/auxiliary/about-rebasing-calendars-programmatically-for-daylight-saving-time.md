---
title: 关于以编程方式为夏令时变基日历
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 38b342d9-ab10-04b6-5490-9a45f847a60f
description: 在本主题中, 春季和秋季之间的这一时段称为 DST 期间。
ms.openlocfilehash: 8d9a0ffda89ee9d8847cde59181747588a50e947
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316952"
---
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a>关于以编程方式为夏令时变基日历

许多国家/地区通过推进时钟来观察夏时制 (DST), 以便夜晚的夏季时间更长。 通常通过在弹簧中将时钟设置为1小时, 并将时钟设置为在秋季的一小时后将其设置为完成。 在本主题中, 春季和秋季之间的这一时段称为 DST 期间。 大多数国家/地区在 DST 开始和结束时都有自己的管理法规。 dst 期限的日期可以从年更改为年, 用户必须在每次 DST 管理法规变化时更新其 Microsoft Outlook 日历。 
  
如果使用的是 windows Vista 或更高版本的 windows 版本, 或者启用了 windows 自动更新, 则可能不会受 DST 更改的影响。 否则, 应安装适用于 Windows 的 DST 更新。 无论更新是自动安装、代表由 IT 部门代表还是作为家庭用户安装, 在 dst 期间内发生的某些现有约会在安装了 Windows dst 更新之后, 可能会显示错误次数. 对于定期约会和单实例约会都是如此。 您必须更新这些约会, 才能在 outlook、outlook Web App 和基于协作数据对象 (CDO) 的应用程序中正确显示它们。 由于 DST 的原因, 更新日历上错误显示的约会称为重定日历。
  
Outlook 为用户和 Exchange Server 提供了工具, 为管理员提供了可变基日历的工具。 outlook 提供适用于 outlook 用户的时区数据更新工具。 使用此工具, 用户可以更新自己的日历。 exchange Server 提供了 exchange 日历更新工具, 可帮助管理员避免因将 outlook 工具广泛部署到所有用户而导致的问题, 并确保每个用户正确运行 outlook 工具。
  
除了依赖用户运行时区数据更新工具或管理员运行 Exchange 日历更新工具之外, 第三方 MAPI 客户端软件开发者可以下载 dll tzmovelib.h。 通过使用此程序集, 开发人员可以使用 Outlook 和 Exchange Server 在其日历重定工具中使用的相同 api。 

以下列表显示了日历重定 api:
  
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
    
若要使用日历重定 api 编写约会重定工具, 可以使用以下过程:
  
1. 使用**IOlkApptRebaser:: BeginEnumerateAppointments**和**IOlkApptRebaser:: EndEnumerateAppointments**查找适用于重定的约会。 如有必要, 提供信息以使用户能够决定要变基的约会。 或者, 使用 MAPI 或 Outlook 对象模型来检查约会的时间和定期信息, 方法是分析**PidLidAppointmentTimeZoneDefinitionStartDisplay**、 **PidLidAppointmentTimeZoneDefinitionEndDisplay**、和**PidLidAppointmentTimeZoneDefinitionRecur**属性。 
    
2. 使用**HrCreateApptRebaser**、 **IOlkApptRebaser:: BeginRebaseAppointments**和**IOlkApptRebaser:: EndRebaseAppointments**将约会变基。 
    
若要获取 tzmovelib.h 程序集, 请在 Outlook 2010 中下载 OutlookTimeZoneMoveLibRedist 可再发行安装程序和 tzmovelib.h 头文件[: 辅助引用可再发行组件安装程序和重定日历头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b). 此下载适用于 outlook 2010 和更高版本的 outlook。 OutlookTimeZoneMoveLibRedist 在 C:\Program Files\MsExTmz. 中安装 tzmovelib.h 程序集文件 请注意, 第三方日历重定应用程序只能重新发布安装程序 OutlookTimeZoneMoveLibRedist, 并且不得从安装程序中单独重新发布程序集、tzmovelib.h 或任何其他已提取的组件。
  
## <a name="see-also"></a>另请参阅

- [关于将 TZDEFINITION 保存到流以提交到二进制属性](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [分析二进制属性读取 TZDEFINITION 结构的流](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [分析二进制属性读取 TZREG 结构的流](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [从约会中读取时区属性](how-to-read-time-zone-properties-from-an-appointment.md)
- [夏时制帮助和支持中心](https://support.microsoft.com/gp/cp_dst)
- [如何使用 Exchange 日历更新工具解决夏时制](https://support.microsoft.com/kb/941018)
- [如何使用 Microsoft Office Outlook 的时区数据更新工具解决时区更改](https://support.microsoft.com/kb/931667)

