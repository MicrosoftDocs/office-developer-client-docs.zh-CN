---
title: 关于以编程方式为夏令时变基日历
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 38b342d9-ab10-04b6-5490-9a45f847a60f
description: 在本主题中，此段弹簧年秋季称为 DST 时段。
ms.openlocfilehash: 8d9a0ffda89ee9d8847cde59181747588a50e947
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389020"
---
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a>关于以编程方式为夏令时变基日历

多个国家/地区通过执行时钟以便晚上具有更长时间的夏时制观察夏令时 (DST)。 这通常是由设置时钟小时提前弹簧，并在重新设置时钟一个小时。 在本主题中，此段弹簧年秋季称为 DST 时段。 大多数国家/地区具有自己的 DST 时开始和结束法规。 DST 时段的日期可以更改年，并且用户必须更新他们的 Microsoft Outlook 日历每次 DST 法规更改。 
  
如果您使用的是 Windows Vista 的 Windows 版本或更高版本，或者让自动更新状态的 Windows 上，您可能不会影响 DST 中的更改。 否则，您应为 Windows 安装 DST 更新。 无论是否自动安装更新，作为家庭用户，您代表由 IT 部门或自己 DST 期间发生某些现有约会可能会显示在安装 Windows 的 DST 更新后不正确的时间. 这是定期和单实例约会，则返回 true。 必须更新这些约会在 Outlook、 Outlook Web App 中，基于协作数据对象 (CDO) 上的应用程序中正确显示它们。 更新日历上的显示不正确的约会，由于 DST 称为重定位日历。
  
Outlook 提供了用于用户的工具和 Exchange Server 提供了工具重定基本值日历的管理员。 Outlook 提供了 Outlook 用户的时区数据更新工具。 使用此工具，用户可以更新他们自己的日历。 Exchange Server 提供了可帮助管理员避免结果从 Outlook 工具部署到所有用户的广泛的难题并确保每个用户能够正常运行 Outlook 工具 Exchange 日历更新工具。
  
除了依赖于运行所在的时区数据更新工具的用户或管理员运行 Exchange 日历更新工具，第三方 MAPI 客户端软件开发人员可以下载 DLL，Tzmovelib.dll。 通过使用此程序集，开发人员可以使用相同 Outlook 和 Exchange Server 定位工具其日历中使用的 Api。 

以下列表显示了定位 Api 的日历：
  
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
    
若要编写使用定位 Api 的日历约会调整工具，您可以使用以下过程：
  
1. 使用**IOlkApptRebaser::BeginEnumerateAppointments**和**IOlkApptRebaser::EndEnumerateAppointments**查找用于定位的候选的约会。 如有必要，展示信息以使用户可以决定向重定基本值的约会。 或者，使用 MAPI 或 Outlook 对象模型通过分析**PidLidAppointmentTimeZoneDefinitionStartDisplay**， **PidLidAppointmentTimeZoneDefinitionEndDisplay**，来检查约会的时间和定期信息和**PidLidAppointmentTimeZoneDefinitionRecur**属性。 
    
2. 使用**HrCreateApptRebaser**、 **IOlkApptRebaser::BeginRebaseAppointments**和**IOlkApptRebaser::EndRebaseAppointments**定约会。 
    
若要获取的 Tzmovelib.dll 程序集，请下载 OutlookTimeZoneMoveLibRedist.exe 可再发行组件安装程序和 Tzmovelib.h 头文件在[Outlook 2010： 辅助参考可再发行组件安装程序和头文件定位日历的](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b). 此下载适用于 Outlook 2010 和更高版本的 Outlook。 OutlookTimeZoneMoveLibRedist.exe 安装 C:\Program Files\MsExTmz Tzmovelib.dll 程序集文件。 请注意，第三方日历调整应用程序可以重新分发 installer 仅 OutlookTimeZoneMoveLibRedist.exe，并且必须不得重新分发本程序集、 Tzmovelib.dll，或任何其他从安装程序单独提取组件。
  
## <a name="see-also"></a>另请参阅

- [关于将 TZDEFINITION 保存到流以提交到二进制属性](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [分析二进制属性读取 TZDEFINITION 结构的流](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [分析二进制属性读取 TZREG 结构的流](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [从约会中读取时区属性](how-to-read-time-zone-properties-from-an-appointment.md)
- [夏时制帮助和支持中心](https://support.microsoft.com/gp/cp_dst)
- [如何夏时制解决使用 Exchange 日历更新工具](https://support.microsoft.com/kb/941018)
- [如何解决在使用 Microsoft Office outlook 的时区数据更新工具所在的时区更改](https://support.microsoft.com/kb/931667)

