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
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a><span data-ttu-id="5c042-103">关于以编程方式为夏令时变基日历</span><span class="sxs-lookup"><span data-stu-id="5c042-103">About rebasing calendars programmatically for Daylight Saving Time</span></span>

<span data-ttu-id="5c042-104">许多国家/地区通过推进时钟来观察夏时制 (DST), 以便夜晚的夏季时间更长。</span><span class="sxs-lookup"><span data-stu-id="5c042-104">Many countries observe daylight saving time (DST) by advancing clocks so that evenings have longer daylight.</span></span> <span data-ttu-id="5c042-105">通常通过在弹簧中将时钟设置为1小时, 并将时钟设置为在秋季的一小时后将其设置为完成。</span><span class="sxs-lookup"><span data-stu-id="5c042-105">This is typically done by setting the clock an hour ahead in the spring, and setting the clock an hour back in the fall.</span></span> <span data-ttu-id="5c042-106">在本主题中, 春季和秋季之间的这一时段称为 DST 期间。</span><span class="sxs-lookup"><span data-stu-id="5c042-106">In this topic, this period between the spring and fall is referred to as the DST period.</span></span> <span data-ttu-id="5c042-107">大多数国家/地区在 DST 开始和结束时都有自己的管理法规。</span><span class="sxs-lookup"><span data-stu-id="5c042-107">Most countries have their own regulations for when DST starts and ends.</span></span> <span data-ttu-id="5c042-108">dst 期限的日期可以从年更改为年, 用户必须在每次 DST 管理法规变化时更新其 Microsoft Outlook 日历。</span><span class="sxs-lookup"><span data-stu-id="5c042-108">The dates of the DST period can change from year to year, and users must update their Microsoft Outlook calendar every time that the DST regulations change.</span></span> 
  
<span data-ttu-id="5c042-109">如果使用的是 windows Vista 或更高版本的 windows 版本, 或者启用了 windows 自动更新, 则可能不会受 DST 更改的影响。</span><span class="sxs-lookup"><span data-stu-id="5c042-109">If you use a version of Windows that is Windows Vista or later, or have Windows automatic update turned on, you may not be affected by the change in DST.</span></span> <span data-ttu-id="5c042-110">否则, 应安装适用于 Windows 的 DST 更新。</span><span class="sxs-lookup"><span data-stu-id="5c042-110">Otherwise, you should install DST updates for Windows.</span></span> <span data-ttu-id="5c042-111">无论更新是自动安装、代表由 IT 部门代表还是作为家庭用户安装, 在 dst 期间内发生的某些现有约会在安装了 Windows dst 更新之后, 可能会显示错误次数.</span><span class="sxs-lookup"><span data-stu-id="5c042-111">Regardless of whether the updates are installed automatically, on your behalf by an IT department, or by yourself as a home user, some existing appointments that occur during the DST period might display incorrect times after the DST updates for Windows are installed.</span></span> <span data-ttu-id="5c042-112">对于定期约会和单实例约会都是如此。</span><span class="sxs-lookup"><span data-stu-id="5c042-112">This is true for both recurring and single-instance appointments.</span></span> <span data-ttu-id="5c042-113">您必须更新这些约会, 才能在 outlook、outlook Web App 和基于协作数据对象 (CDO) 的应用程序中正确显示它们。</span><span class="sxs-lookup"><span data-stu-id="5c042-113">You must update these appointments to display them correctly in Outlook, in Outlook Web App, and in applications that are based on Collaboration Data Objects (CDO).</span></span> <span data-ttu-id="5c042-114">由于 DST 的原因, 更新日历上错误显示的约会称为重定日历。</span><span class="sxs-lookup"><span data-stu-id="5c042-114">Updating incorrectly displayed appointments on calendars because of DST is known as rebasing calendars.</span></span>
  
<span data-ttu-id="5c042-115">Outlook 为用户和 Exchange Server 提供了工具, 为管理员提供了可变基日历的工具。</span><span class="sxs-lookup"><span data-stu-id="5c042-115">Outlook provides tools for users and Exchange Server provides tools for administrators to rebase calendars.</span></span> <span data-ttu-id="5c042-116">outlook 提供适用于 outlook 用户的时区数据更新工具。</span><span class="sxs-lookup"><span data-stu-id="5c042-116">Outlook provides the Time Zone Data Update Tool for Outlook users.</span></span> <span data-ttu-id="5c042-117">使用此工具, 用户可以更新自己的日历。</span><span class="sxs-lookup"><span data-stu-id="5c042-117">With this tool, users can update their own calendars.</span></span> <span data-ttu-id="5c042-118">exchange Server 提供了 exchange 日历更新工具, 可帮助管理员避免因将 outlook 工具广泛部署到所有用户而导致的问题, 并确保每个用户正确运行 outlook 工具。</span><span class="sxs-lookup"><span data-stu-id="5c042-118">Exchange Server provides the Exchange Calendar Update Tool that helps administrators to avoid difficulties that result from deploying the Outlook tool widely to all users and to make sure that each user runs the Outlook tool correctly.</span></span>
  
<span data-ttu-id="5c042-119">除了依赖用户运行时区数据更新工具或管理员运行 Exchange 日历更新工具之外, 第三方 MAPI 客户端软件开发者可以下载 dll tzmovelib.h。</span><span class="sxs-lookup"><span data-stu-id="5c042-119">In addition to relying on users to run the Time Zone Data Update Tool or administrators to run the Exchange Calendar Update Tool, third-party MAPI client software developers can download a DLL, Tzmovelib.dll.</span></span> <span data-ttu-id="5c042-120">通过使用此程序集, 开发人员可以使用 Outlook 和 Exchange Server 在其日历重定工具中使用的相同 api。</span><span class="sxs-lookup"><span data-stu-id="5c042-120">By using this assembly, developers can use the same APIs that Outlook and Exchange Server use in their calendar rebasing tools.</span></span> 

<span data-ttu-id="5c042-121">以下列表显示了日历重定 api:</span><span class="sxs-lookup"><span data-stu-id="5c042-121">The following list shows the calendar rebasing APIs:</span></span>
  
- [<span data-ttu-id="5c042-122">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="5c042-122">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
    
- [<span data-ttu-id="5c042-123">IOlkApptRebaser</span><span class="sxs-lookup"><span data-stu-id="5c042-123">IOlkApptRebaser</span></span>](iolkapptrebaser.md)
    
- [<span data-ttu-id="5c042-124">IOlkApptRebaser::BeginEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="5c042-124">IOlkApptRebaser::BeginEnumerateAppointments</span></span>](iolkapptrebaser-beginenumerateappointments.md)
    
- [<span data-ttu-id="5c042-125">IOlkApptRebaser::BeginRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="5c042-125">IOlkApptRebaser::BeginRebaseAppointments</span></span>](iolkapptrebaser-beginrebaseappointments.md)
    
- [<span data-ttu-id="5c042-126">IOlkApptRebaser::EndEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="5c042-126">IOlkApptRebaser::EndEnumerateAppointments</span></span>](iolkapptrebaser-endenumerateappointments.md)
    
- [<span data-ttu-id="5c042-127">IOlkApptRebaser::EndRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="5c042-127">IOlkApptRebaser::EndRebaseAppointments</span></span>](iolkapptrebaser-endrebaseappointments.md)
    
- [<span data-ttu-id="5c042-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span><span class="sxs-lookup"><span data-stu-id="5c042-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span></span>](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)
    
- [<span data-ttu-id="5c042-129">PidLidAppointmentTimeZoneDefinitionRecur</span><span class="sxs-lookup"><span data-stu-id="5c042-129">PidLidAppointmentTimeZoneDefinitionRecur</span></span>](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)
    
- [<span data-ttu-id="5c042-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span><span class="sxs-lookup"><span data-stu-id="5c042-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span></span>](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)
    
- [<span data-ttu-id="5c042-131">PidLidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="5c042-131">PidLidTimeZoneStruct</span></span>](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)
    
- [<span data-ttu-id="5c042-132">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="5c042-132">RebaseTaskComplete</span></span>](rebasetaskcomplete.md)
    
- [<span data-ttu-id="5c042-133">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="5c042-133">RebaseTaskProgress</span></span>](rebasetaskprogress.md)
    
- [<span data-ttu-id="5c042-134">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="5c042-134">TZDEFINITION</span></span>](tzdefinition.md)
    
- [<span data-ttu-id="5c042-135">TZREG</span><span class="sxs-lookup"><span data-stu-id="5c042-135">TZREG</span></span>](tzreg.md)
    
- [<span data-ttu-id="5c042-136">TZRULE</span><span class="sxs-lookup"><span data-stu-id="5c042-136">TZRULE</span></span>](tzrule.md)
    
<span data-ttu-id="5c042-137">若要使用日历重定 api 编写约会重定工具, 可以使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="5c042-137">To write an appointment rebasing tool by using the calendar rebasing APIs, you can use the following procedure:</span></span>
  
1. <span data-ttu-id="5c042-138">使用**IOlkApptRebaser:: BeginEnumerateAppointments**和**IOlkApptRebaser:: EndEnumerateAppointments**查找适用于重定的约会。</span><span class="sxs-lookup"><span data-stu-id="5c042-138">Use **IOlkApptRebaser::BeginEnumerateAppointments** and **IOlkApptRebaser::EndEnumerateAppointments** to find appointments that are candidates for rebasing.</span></span> <span data-ttu-id="5c042-139">如有必要, 提供信息以使用户能够决定要变基的约会。</span><span class="sxs-lookup"><span data-stu-id="5c042-139">If necessary, present information to enable the user to decide which appointments to rebase.</span></span> <span data-ttu-id="5c042-140">或者, 使用 MAPI 或 Outlook 对象模型来检查约会的时间和定期信息, 方法是分析**PidLidAppointmentTimeZoneDefinitionStartDisplay**、 **PidLidAppointmentTimeZoneDefinitionEndDisplay**、和**PidLidAppointmentTimeZoneDefinitionRecur**属性。</span><span class="sxs-lookup"><span data-stu-id="5c042-140">Alternatively, use MAPI or the Outlook Object Model to examine the time and recurrence information for an appointment by parsing the **PidLidAppointmentTimeZoneDefinitionStartDisplay**, **PidLidAppointmentTimeZoneDefinitionEndDisplay**, and **PidLidAppointmentTimeZoneDefinitionRecur** properties.</span></span> 
    
2. <span data-ttu-id="5c042-141">使用**HrCreateApptRebaser**、 **IOlkApptRebaser:: BeginRebaseAppointments**和**IOlkApptRebaser:: EndRebaseAppointments**将约会变基。</span><span class="sxs-lookup"><span data-stu-id="5c042-141">Use **HrCreateApptRebaser**, **IOlkApptRebaser::BeginRebaseAppointments**, and **IOlkApptRebaser::EndRebaseAppointments** to rebase the appointment.</span></span> 
    
<span data-ttu-id="5c042-142">若要获取 tzmovelib.h 程序集, 请在 Outlook 2010 中下载 OutlookTimeZoneMoveLibRedist 可再发行安装程序和 tzmovelib.h 头文件[: 辅助引用可再发行组件安装程序和重定日历头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).</span><span class="sxs-lookup"><span data-stu-id="5c042-142">To obtain the Tzmovelib.dll assembly, download the OutlookTimeZoneMoveLibRedist.exe redistributable installer and the Tzmovelib.h header file at [Outlook 2010: Auxiliary Reference Redistributable Installer and Header File for Rebasing Calendars](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).</span></span> <span data-ttu-id="5c042-143">此下载适用于 outlook 2010 和更高版本的 outlook。</span><span class="sxs-lookup"><span data-stu-id="5c042-143">This download works for Outlook 2010 and later versions of Outlook.</span></span> <span data-ttu-id="5c042-144">OutlookTimeZoneMoveLibRedist 在 C:\Program Files\MsExTmz. 中安装 tzmovelib.h 程序集文件</span><span class="sxs-lookup"><span data-stu-id="5c042-144">OutlookTimeZoneMoveLibRedist.exe installs the Tzmovelib.dll assembly file in C:\Program Files\MsExTmz.</span></span> <span data-ttu-id="5c042-145">请注意, 第三方日历重定应用程序只能重新发布安装程序 OutlookTimeZoneMoveLibRedist, 并且不得从安装程序中单独重新发布程序集、tzmovelib.h 或任何其他已提取的组件。</span><span class="sxs-lookup"><span data-stu-id="5c042-145">Note that third-party calendar rebasing applications can redistribute only the installer, OutlookTimeZoneMoveLibRedist.exe, and must not redistribute the assembly, Tzmovelib.dll, or any other extracted components separately from the installer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c042-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c042-146">See also</span></span>

- [<span data-ttu-id="5c042-147">关于将 TZDEFINITION 保存到流以提交到二进制属性</span><span class="sxs-lookup"><span data-stu-id="5c042-147">About persisting TZDEFINITION to a stream to commit to a binary property</span></span>](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [<span data-ttu-id="5c042-148">分析二进制属性读取 TZDEFINITION 结构的流</span><span class="sxs-lookup"><span data-stu-id="5c042-148">Parse a stream from a binary property to read the TZDEFINITION structure</span></span>](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [<span data-ttu-id="5c042-149">分析二进制属性读取 TZREG 结构的流</span><span class="sxs-lookup"><span data-stu-id="5c042-149">Parse a stream from a binary property to read the TZREG structure</span></span>](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [<span data-ttu-id="5c042-150">从约会中读取时区属性</span><span class="sxs-lookup"><span data-stu-id="5c042-150">Read time zone properties from an appointment</span></span>](how-to-read-time-zone-properties-from-an-appointment.md)
- [<span data-ttu-id="5c042-151">夏时制帮助和支持中心</span><span class="sxs-lookup"><span data-stu-id="5c042-151">Daylight Saving Time Help and Support Center</span></span>](https://support.microsoft.com/gp/cp_dst)
- [<span data-ttu-id="5c042-152">如何使用 Exchange 日历更新工具解决夏时制</span><span class="sxs-lookup"><span data-stu-id="5c042-152">How to address daylight saving time by using the Exchange Calendar Update Tool</span></span>](https://support.microsoft.com/kb/941018)
- [<span data-ttu-id="5c042-153">如何使用 Microsoft Office Outlook 的时区数据更新工具解决时区更改</span><span class="sxs-lookup"><span data-stu-id="5c042-153">How to address time zone changes by using the Time Zone Data Update Tool for Microsoft Office Outlook</span></span>](https://support.microsoft.com/kb/931667)

