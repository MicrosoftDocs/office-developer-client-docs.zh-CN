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
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a><span data-ttu-id="13cec-103">关于以编程方式为夏令时变基日历</span><span class="sxs-lookup"><span data-stu-id="13cec-103">About rebasing calendars programmatically for Daylight Saving Time</span></span>

<span data-ttu-id="13cec-104">多个国家/地区通过执行时钟以便晚上具有更长时间的夏时制观察夏令时 (DST)。</span><span class="sxs-lookup"><span data-stu-id="13cec-104">Many countries observe daylight saving time (DST) by advancing clocks so that evenings have longer daylight.</span></span> <span data-ttu-id="13cec-105">这通常是由设置时钟小时提前弹簧，并在重新设置时钟一个小时。</span><span class="sxs-lookup"><span data-stu-id="13cec-105">This is typically done by setting the clock an hour ahead in the spring, and setting the clock an hour back in the fall.</span></span> <span data-ttu-id="13cec-106">在本主题中，此段弹簧年秋季称为 DST 时段。</span><span class="sxs-lookup"><span data-stu-id="13cec-106">In this topic, this period between the spring and fall is referred to as the DST period.</span></span> <span data-ttu-id="13cec-107">大多数国家/地区具有自己的 DST 时开始和结束法规。</span><span class="sxs-lookup"><span data-stu-id="13cec-107">Most countries have their own regulations for when DST starts and ends.</span></span> <span data-ttu-id="13cec-108">DST 时段的日期可以更改年，并且用户必须更新他们的 Microsoft Outlook 日历每次 DST 法规更改。</span><span class="sxs-lookup"><span data-stu-id="13cec-108">The dates of the DST period can change from year to year, and users must update their Microsoft Outlook calendar every time that the DST regulations change.</span></span> 
  
<span data-ttu-id="13cec-109">如果您使用的是 Windows Vista 的 Windows 版本或更高版本，或者让自动更新状态的 Windows 上，您可能不会影响 DST 中的更改。</span><span class="sxs-lookup"><span data-stu-id="13cec-109">If you use a version of Windows that is Windows Vista or later, or have Windows automatic update turned on, you may not be affected by the change in DST.</span></span> <span data-ttu-id="13cec-110">否则，您应为 Windows 安装 DST 更新。</span><span class="sxs-lookup"><span data-stu-id="13cec-110">Otherwise, you should install DST updates for Windows.</span></span> <span data-ttu-id="13cec-111">无论是否自动安装更新，作为家庭用户，您代表由 IT 部门或自己 DST 期间发生某些现有约会可能会显示在安装 Windows 的 DST 更新后不正确的时间.</span><span class="sxs-lookup"><span data-stu-id="13cec-111">Regardless of whether the updates are installed automatically, on your behalf by an IT department, or by yourself as a home user, some existing appointments that occur during the DST period might display incorrect times after the DST updates for Windows are installed.</span></span> <span data-ttu-id="13cec-112">这是定期和单实例约会，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="13cec-112">This is true for both recurring and single-instance appointments.</span></span> <span data-ttu-id="13cec-113">必须更新这些约会在 Outlook、 Outlook Web App 中，基于协作数据对象 (CDO) 上的应用程序中正确显示它们。</span><span class="sxs-lookup"><span data-stu-id="13cec-113">You must update these appointments to display them correctly in Outlook, in Outlook Web App, and in applications that are based on Collaboration Data Objects (CDO).</span></span> <span data-ttu-id="13cec-114">更新日历上的显示不正确的约会，由于 DST 称为重定位日历。</span><span class="sxs-lookup"><span data-stu-id="13cec-114">Updating incorrectly displayed appointments on calendars because of DST is known as rebasing calendars.</span></span>
  
<span data-ttu-id="13cec-115">Outlook 提供了用于用户的工具和 Exchange Server 提供了工具重定基本值日历的管理员。</span><span class="sxs-lookup"><span data-stu-id="13cec-115">Outlook provides tools for users and Exchange Server provides tools for administrators to rebase calendars.</span></span> <span data-ttu-id="13cec-116">Outlook 提供了 Outlook 用户的时区数据更新工具。</span><span class="sxs-lookup"><span data-stu-id="13cec-116">Outlook provides the Time Zone Data Update Tool for Outlook users.</span></span> <span data-ttu-id="13cec-117">使用此工具，用户可以更新他们自己的日历。</span><span class="sxs-lookup"><span data-stu-id="13cec-117">With this tool, users can update their own calendars.</span></span> <span data-ttu-id="13cec-118">Exchange Server 提供了可帮助管理员避免结果从 Outlook 工具部署到所有用户的广泛的难题并确保每个用户能够正常运行 Outlook 工具 Exchange 日历更新工具。</span><span class="sxs-lookup"><span data-stu-id="13cec-118">Exchange Server provides the Exchange Calendar Update Tool that helps administrators to avoid difficulties that result from deploying the Outlook tool widely to all users and to make sure that each user runs the Outlook tool correctly.</span></span>
  
<span data-ttu-id="13cec-119">除了依赖于运行所在的时区数据更新工具的用户或管理员运行 Exchange 日历更新工具，第三方 MAPI 客户端软件开发人员可以下载 DLL，Tzmovelib.dll。</span><span class="sxs-lookup"><span data-stu-id="13cec-119">In addition to relying on users to run the Time Zone Data Update Tool or administrators to run the Exchange Calendar Update Tool, third-party MAPI client software developers can download a DLL, Tzmovelib.dll.</span></span> <span data-ttu-id="13cec-120">通过使用此程序集，开发人员可以使用相同 Outlook 和 Exchange Server 定位工具其日历中使用的 Api。</span><span class="sxs-lookup"><span data-stu-id="13cec-120">By using this assembly, developers can use the same APIs that Outlook and Exchange Server use in their calendar rebasing tools.</span></span> 

<span data-ttu-id="13cec-121">以下列表显示了定位 Api 的日历：</span><span class="sxs-lookup"><span data-stu-id="13cec-121">The following list shows the calendar rebasing APIs:</span></span>
  
- [<span data-ttu-id="13cec-122">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="13cec-122">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
    
- [<span data-ttu-id="13cec-123">IOlkApptRebaser</span><span class="sxs-lookup"><span data-stu-id="13cec-123">IOlkApptRebaser</span></span>](iolkapptrebaser.md)
    
- [<span data-ttu-id="13cec-124">IOlkApptRebaser::BeginEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="13cec-124">IOlkApptRebaser::BeginEnumerateAppointments</span></span>](iolkapptrebaser-beginenumerateappointments.md)
    
- [<span data-ttu-id="13cec-125">IOlkApptRebaser::BeginRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="13cec-125">IOlkApptRebaser::BeginRebaseAppointments</span></span>](iolkapptrebaser-beginrebaseappointments.md)
    
- [<span data-ttu-id="13cec-126">IOlkApptRebaser::EndEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="13cec-126">IOlkApptRebaser::EndEnumerateAppointments</span></span>](iolkapptrebaser-endenumerateappointments.md)
    
- [<span data-ttu-id="13cec-127">IOlkApptRebaser::EndRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="13cec-127">IOlkApptRebaser::EndRebaseAppointments</span></span>](iolkapptrebaser-endrebaseappointments.md)
    
- [<span data-ttu-id="13cec-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span><span class="sxs-lookup"><span data-stu-id="13cec-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span></span>](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)
    
- [<span data-ttu-id="13cec-129">PidLidAppointmentTimeZoneDefinitionRecur</span><span class="sxs-lookup"><span data-stu-id="13cec-129">PidLidAppointmentTimeZoneDefinitionRecur</span></span>](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)
    
- [<span data-ttu-id="13cec-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span><span class="sxs-lookup"><span data-stu-id="13cec-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span></span>](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)
    
- [<span data-ttu-id="13cec-131">PidLidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="13cec-131">PidLidTimeZoneStruct</span></span>](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)
    
- [<span data-ttu-id="13cec-132">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="13cec-132">RebaseTaskComplete</span></span>](rebasetaskcomplete.md)
    
- [<span data-ttu-id="13cec-133">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="13cec-133">RebaseTaskProgress</span></span>](rebasetaskprogress.md)
    
- [<span data-ttu-id="13cec-134">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="13cec-134">TZDEFINITION</span></span>](tzdefinition.md)
    
- [<span data-ttu-id="13cec-135">TZREG</span><span class="sxs-lookup"><span data-stu-id="13cec-135">TZREG</span></span>](tzreg.md)
    
- [<span data-ttu-id="13cec-136">TZRULE</span><span class="sxs-lookup"><span data-stu-id="13cec-136">TZRULE</span></span>](tzrule.md)
    
<span data-ttu-id="13cec-137">若要编写使用定位 Api 的日历约会调整工具，您可以使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="13cec-137">To write an appointment rebasing tool by using the calendar rebasing APIs, you can use the following procedure:</span></span>
  
1. <span data-ttu-id="13cec-138">使用**IOlkApptRebaser::BeginEnumerateAppointments**和**IOlkApptRebaser::EndEnumerateAppointments**查找用于定位的候选的约会。</span><span class="sxs-lookup"><span data-stu-id="13cec-138">Use **IOlkApptRebaser::BeginEnumerateAppointments** and **IOlkApptRebaser::EndEnumerateAppointments** to find appointments that are candidates for rebasing.</span></span> <span data-ttu-id="13cec-139">如有必要，展示信息以使用户可以决定向重定基本值的约会。</span><span class="sxs-lookup"><span data-stu-id="13cec-139">If necessary, present information to enable the user to decide which appointments to rebase.</span></span> <span data-ttu-id="13cec-140">或者，使用 MAPI 或 Outlook 对象模型通过分析**PidLidAppointmentTimeZoneDefinitionStartDisplay**， **PidLidAppointmentTimeZoneDefinitionEndDisplay**，来检查约会的时间和定期信息和**PidLidAppointmentTimeZoneDefinitionRecur**属性。</span><span class="sxs-lookup"><span data-stu-id="13cec-140">Alternatively, use MAPI or the Outlook Object Model to examine the time and recurrence information for an appointment by parsing the **PidLidAppointmentTimeZoneDefinitionStartDisplay**, **PidLidAppointmentTimeZoneDefinitionEndDisplay**, and **PidLidAppointmentTimeZoneDefinitionRecur** properties.</span></span> 
    
2. <span data-ttu-id="13cec-141">使用**HrCreateApptRebaser**、 **IOlkApptRebaser::BeginRebaseAppointments**和**IOlkApptRebaser::EndRebaseAppointments**定约会。</span><span class="sxs-lookup"><span data-stu-id="13cec-141">Use **HrCreateApptRebaser**, **IOlkApptRebaser::BeginRebaseAppointments**, and **IOlkApptRebaser::EndRebaseAppointments** to rebase the appointment.</span></span> 
    
<span data-ttu-id="13cec-142">若要获取的 Tzmovelib.dll 程序集，请下载 OutlookTimeZoneMoveLibRedist.exe 可再发行组件安装程序和 Tzmovelib.h 头文件在[Outlook 2010： 辅助参考可再发行组件安装程序和头文件定位日历的](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).</span><span class="sxs-lookup"><span data-stu-id="13cec-142">To obtain the Tzmovelib.dll assembly, download the OutlookTimeZoneMoveLibRedist.exe redistributable installer and the Tzmovelib.h header file at [Outlook 2010: Auxiliary Reference Redistributable Installer and Header File for Rebasing Calendars](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).</span></span> <span data-ttu-id="13cec-143">此下载适用于 Outlook 2010 和更高版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="13cec-143">This download works for Outlook 2010 and later versions of Outlook.</span></span> <span data-ttu-id="13cec-144">OutlookTimeZoneMoveLibRedist.exe 安装 C:\Program Files\MsExTmz Tzmovelib.dll 程序集文件。</span><span class="sxs-lookup"><span data-stu-id="13cec-144">OutlookTimeZoneMoveLibRedist.exe installs the Tzmovelib.dll assembly file in C:\Program Files\MsExTmz.</span></span> <span data-ttu-id="13cec-145">请注意，第三方日历调整应用程序可以重新分发 installer 仅 OutlookTimeZoneMoveLibRedist.exe，并且必须不得重新分发本程序集、 Tzmovelib.dll，或任何其他从安装程序单独提取组件。</span><span class="sxs-lookup"><span data-stu-id="13cec-145">Note that third-party calendar rebasing applications can redistribute only the installer, OutlookTimeZoneMoveLibRedist.exe, and must not redistribute the assembly, Tzmovelib.dll, or any other extracted components separately from the installer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13cec-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13cec-146">See also</span></span>

- [<span data-ttu-id="13cec-147">关于将 TZDEFINITION 保存到流以提交到二进制属性</span><span class="sxs-lookup"><span data-stu-id="13cec-147">About persisting TZDEFINITION to a stream to commit to a binary property</span></span>](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [<span data-ttu-id="13cec-148">分析二进制属性读取 TZDEFINITION 结构的流</span><span class="sxs-lookup"><span data-stu-id="13cec-148">Parse a stream from a binary property to read the TZDEFINITION structure</span></span>](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [<span data-ttu-id="13cec-149">分析二进制属性读取 TZREG 结构的流</span><span class="sxs-lookup"><span data-stu-id="13cec-149">Parse a stream from a binary property to read the TZREG structure</span></span>](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [<span data-ttu-id="13cec-150">从约会中读取时区属性</span><span class="sxs-lookup"><span data-stu-id="13cec-150">Read time zone properties from an appointment</span></span>](how-to-read-time-zone-properties-from-an-appointment.md)
- [<span data-ttu-id="13cec-151">夏时制帮助和支持中心</span><span class="sxs-lookup"><span data-stu-id="13cec-151">Daylight Saving Time Help and Support Center</span></span>](https://support.microsoft.com/gp/cp_dst)
- [<span data-ttu-id="13cec-152">如何夏时制解决使用 Exchange 日历更新工具</span><span class="sxs-lookup"><span data-stu-id="13cec-152">How to address daylight saving time by using the Exchange Calendar Update Tool</span></span>](https://support.microsoft.com/kb/941018)
- [<span data-ttu-id="13cec-153">如何解决在使用 Microsoft Office outlook 的时区数据更新工具所在的时区更改</span><span class="sxs-lookup"><span data-stu-id="13cec-153">How to address time zone changes by using the Time Zone Data Update Tool for Microsoft Office Outlook</span></span>](https://support.microsoft.com/kb/931667)

