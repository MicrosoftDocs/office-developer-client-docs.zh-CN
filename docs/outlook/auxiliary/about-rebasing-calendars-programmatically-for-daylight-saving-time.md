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
# <a name="about-rebasing-calendars-programmatically-for-daylight-saving-time"></a><span data-ttu-id="fbf64-103">关于以编程方式为夏令时变基日历</span><span class="sxs-lookup"><span data-stu-id="fbf64-103">About rebasing calendars programmatically for Daylight Saving Time</span></span>

<span data-ttu-id="fbf64-104">多个国家/地区都遵循夏令时 (DST) 延长时钟，以便晚上的夏时制时间更长。</span><span class="sxs-lookup"><span data-stu-id="fbf64-104">Many countries observe daylight saving time (DST) by advancing clocks so that evenings have longer daylight.</span></span> <span data-ttu-id="fbf64-105">这通常是通过设置弹簧中提前一小时时钟，在秋季将时钟设置回一小时。</span><span class="sxs-lookup"><span data-stu-id="fbf64-105">This is typically done by setting the clock an hour ahead in the spring, and setting the clock an hour back in the fall.</span></span> <span data-ttu-id="fbf64-106">在本主题中，在弹簧和秋季之间的这一时段称为 DST 时段。</span><span class="sxs-lookup"><span data-stu-id="fbf64-106">In this topic, this period between the spring and fall is referred to as the DST period.</span></span> <span data-ttu-id="fbf64-107">对于 DST 的开始和结束时间，大多数国家/地区都有自己的法规。</span><span class="sxs-lookup"><span data-stu-id="fbf64-107">Most countries have their own regulations for when DST starts and ends.</span></span> <span data-ttu-id="fbf64-108">DST 时段的日期可能会因年而变，用户必须每次 DST Outlook更改时更新其 Microsoft 日历。</span><span class="sxs-lookup"><span data-stu-id="fbf64-108">The dates of the DST period can change from year to year, and users must update their Microsoft Outlook calendar every time that the DST regulations change.</span></span> 
  
<span data-ttu-id="fbf64-109">如果使用 Vista Windows或更高版本Windows版本，或打开 Windows 自动更新，则 DST 中的更改可能不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="fbf64-109">If you use a version of Windows that is Windows Vista or later, or have Windows automatic update turned on, you may not be affected by the change in DST.</span></span> <span data-ttu-id="fbf64-110">否则，应安装 DST 更新Windows。</span><span class="sxs-lookup"><span data-stu-id="fbf64-110">Otherwise, you should install DST updates for Windows.</span></span> <span data-ttu-id="fbf64-111">无论更新是自动安装的，还是由 IT 部门代表您安装的，或者您自己作为主用户安装的，DST 期间发生的某些现有约会在安装 Windows 的 DST 更新后可能显示错误的时间。</span><span class="sxs-lookup"><span data-stu-id="fbf64-111">Regardless of whether the updates are installed automatically, on your behalf by an IT department, or by yourself as a home user, some existing appointments that occur during the DST period might display incorrect times after the DST updates for Windows are installed.</span></span> <span data-ttu-id="fbf64-112">定期约会和单实例约会均如此。</span><span class="sxs-lookup"><span data-stu-id="fbf64-112">This is true for both recurring and single-instance appointments.</span></span> <span data-ttu-id="fbf64-113">必须更新这些约会，以在 Outlook、Outlook Web App 以及基于协作数据对象 (CDO) 的应用程序中正确显示这些约会。</span><span class="sxs-lookup"><span data-stu-id="fbf64-113">You must update these appointments to display them correctly in Outlook, in Outlook Web App, and in applications that are based on Collaboration Data Objects (CDO).</span></span> <span data-ttu-id="fbf64-114">由于 DST，更新日历上显示不正确的约会称为重基于日历。</span><span class="sxs-lookup"><span data-stu-id="fbf64-114">Updating incorrectly displayed appointments on calendars because of DST is known as rebasing calendars.</span></span>
  
<span data-ttu-id="fbf64-115">Outlook为用户提供工具，Exchange Server为管理员提供重基于日历的工具。</span><span class="sxs-lookup"><span data-stu-id="fbf64-115">Outlook provides tools for users and Exchange Server provides tools for administrators to rebase calendars.</span></span> <span data-ttu-id="fbf64-116">Outlook为用户提供时区数据更新Outlook工具。</span><span class="sxs-lookup"><span data-stu-id="fbf64-116">Outlook provides the Time Zone Data Update Tool for Outlook users.</span></span> <span data-ttu-id="fbf64-117">使用此工具，用户可以更新自己的日历。</span><span class="sxs-lookup"><span data-stu-id="fbf64-117">With this tool, users can update their own calendars.</span></span> <span data-ttu-id="fbf64-118">Exchange Server提供了 Exchange 日历更新工具，可帮助管理员避免因将 Outlook 工具广泛部署到所有用户而造成困难，并确保每个用户正确运行 Outlook 工具。</span><span class="sxs-lookup"><span data-stu-id="fbf64-118">Exchange Server provides the Exchange Calendar Update Tool that helps administrators to avoid difficulties that result from deploying the Outlook tool widely to all users and to make sure that each user runs the Outlook tool correctly.</span></span>
  
<span data-ttu-id="fbf64-119">除了依赖用户运行时区数据更新工具或管理员来运行 Exchange 日历更新工具之外，第三方 MAPI 客户端软件开发人员还可以下载 DLL，Tzmovelib.dll。</span><span class="sxs-lookup"><span data-stu-id="fbf64-119">In addition to relying on users to run the Time Zone Data Update Tool or administrators to run the Exchange Calendar Update Tool, third-party MAPI client software developers can download a DLL, Tzmovelib.dll.</span></span> <span data-ttu-id="fbf64-120">通过使用此程序集，开发人员可以使用与日历重基Outlook和Exchange Server相同的 API。</span><span class="sxs-lookup"><span data-stu-id="fbf64-120">By using this assembly, developers can use the same APIs that Outlook and Exchange Server use in their calendar rebasing tools.</span></span> 

<span data-ttu-id="fbf64-121">以下列表显示了日历重基 API：</span><span class="sxs-lookup"><span data-stu-id="fbf64-121">The following list shows the calendar rebasing APIs:</span></span>
  
- [<span data-ttu-id="fbf64-122">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="fbf64-122">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
    
- [<span data-ttu-id="fbf64-123">IOlkApptRebaser</span><span class="sxs-lookup"><span data-stu-id="fbf64-123">IOlkApptRebaser</span></span>](iolkapptrebaser.md)
    
- [<span data-ttu-id="fbf64-124">IOlkApptRebaser::BeginEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="fbf64-124">IOlkApptRebaser::BeginEnumerateAppointments</span></span>](iolkapptrebaser-beginenumerateappointments.md)
    
- [<span data-ttu-id="fbf64-125">IOlkApptRebaser::BeginRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="fbf64-125">IOlkApptRebaser::BeginRebaseAppointments</span></span>](iolkapptrebaser-beginrebaseappointments.md)
    
- [<span data-ttu-id="fbf64-126">IOlkApptRebaser::EndEnumerateAppointments</span><span class="sxs-lookup"><span data-stu-id="fbf64-126">IOlkApptRebaser::EndEnumerateAppointments</span></span>](iolkapptrebaser-endenumerateappointments.md)
    
- [<span data-ttu-id="fbf64-127">IOlkApptRebaser::EndRebaseAppointments</span><span class="sxs-lookup"><span data-stu-id="fbf64-127">IOlkApptRebaser::EndRebaseAppointments</span></span>](iolkapptrebaser-endrebaseappointments.md)
    
- [<span data-ttu-id="fbf64-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span><span class="sxs-lookup"><span data-stu-id="fbf64-128">PidLidAppointmentTimeZoneDefinitionEndDisplay</span></span>](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)
    
- [<span data-ttu-id="fbf64-129">PidLidAppointmentTimeZoneDefinitionRecur</span><span class="sxs-lookup"><span data-stu-id="fbf64-129">PidLidAppointmentTimeZoneDefinitionRecur</span></span>](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)
    
- [<span data-ttu-id="fbf64-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span><span class="sxs-lookup"><span data-stu-id="fbf64-130">PidLidAppointmentTimeZoneDefinitionStartDisplay</span></span>](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)
    
- [<span data-ttu-id="fbf64-131">PidLidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="fbf64-131">PidLidTimeZoneStruct</span></span>](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)
    
- [<span data-ttu-id="fbf64-132">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="fbf64-132">RebaseTaskComplete</span></span>](rebasetaskcomplete.md)
    
- [<span data-ttu-id="fbf64-133">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="fbf64-133">RebaseTaskProgress</span></span>](rebasetaskprogress.md)
    
- [<span data-ttu-id="fbf64-134">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="fbf64-134">TZDEFINITION</span></span>](tzdefinition.md)
    
- [<span data-ttu-id="fbf64-135">TZREG</span><span class="sxs-lookup"><span data-stu-id="fbf64-135">TZREG</span></span>](tzreg.md)
    
- [<span data-ttu-id="fbf64-136">TZRULE</span><span class="sxs-lookup"><span data-stu-id="fbf64-136">TZRULE</span></span>](tzrule.md)
    
<span data-ttu-id="fbf64-137">若要使用日历重基基 API 编写约会重基工具，可以使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="fbf64-137">To write an appointment rebasing tool by using the calendar rebasing APIs, you can use the following procedure:</span></span>
  
1. <span data-ttu-id="fbf64-138">使用 **IOlkApptRebaser：：BeginEnumerateAppointments** 和 **IOlkApptRebaser：：EndEnumerateAppointments** 查找作为重基的候选约会。</span><span class="sxs-lookup"><span data-stu-id="fbf64-138">Use **IOlkApptRebaser::BeginEnumerateAppointments** and **IOlkApptRebaser::EndEnumerateAppointments** to find appointments that are candidates for rebasing.</span></span> <span data-ttu-id="fbf64-139">如有必要，提供使用户能够决定要重定基底的约会的信息。</span><span class="sxs-lookup"><span data-stu-id="fbf64-139">If necessary, present information to enable the user to decide which appointments to rebase.</span></span> <span data-ttu-id="fbf64-140">或者，使用 MAPI 或 Outlook 对象模型通过分析 **PidLidAppointmentTimeZoneDefinitionStartDisplay、PidLidAppointmentTimeZoneDefinitionEndDisplay** 和 **PidLidAppointmentTimeZoneDefinitionRecur** 属性来检查约会的时间和定期信息。</span><span class="sxs-lookup"><span data-stu-id="fbf64-140">Alternatively, use MAPI or the Outlook Object Model to examine the time and recurrence information for an appointment by parsing the **PidLidAppointmentTimeZoneDefinitionStartDisplay**, **PidLidAppointmentTimeZoneDefinitionEndDisplay**, and **PidLidAppointmentTimeZoneDefinitionRecur** properties.</span></span> 
    
2. <span data-ttu-id="fbf64-141">使用 **HrCreateApptRebaser、IOlkApptRebaser：：BeginRebaseAppointments** 和 **IOlkApptRebaser：：EndRebaseAppointments** 重设定约会基本值。 </span><span class="sxs-lookup"><span data-stu-id="fbf64-141">Use **HrCreateApptRebaser**, **IOlkApptRebaser::BeginRebaseAppointments**, and **IOlkApptRebaser::EndRebaseAppointments** to rebase the appointment.</span></span> 
    
<span data-ttu-id="fbf64-142">若要获取 Tzmovelib.dll 程序集，请下载 OutlookTimeZoneMoveLibRedist.exe 可再发行组件安装程序和 Tzmovelib.h 头文件，位置为[Outlook 2010：用于](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b)重基日历的辅助参考可再发行组件安装程序和头文件。</span><span class="sxs-lookup"><span data-stu-id="fbf64-142">To obtain the Tzmovelib.dll assembly, download the OutlookTimeZoneMoveLibRedist.exe redistributable installer and the Tzmovelib.h header file at [Outlook 2010: Auxiliary Reference Redistributable Installer and Header File for Rebasing Calendars](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).</span></span> <span data-ttu-id="fbf64-143">此下载适用于 Outlook 2010 及更高版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="fbf64-143">This download works for Outlook 2010 and later versions of Outlook.</span></span> <span data-ttu-id="fbf64-144">OutlookTimeZoneMoveLibRedist.exe C：\Program Files\msExTmz Tzmovelib.dll程序集文件。</span><span class="sxs-lookup"><span data-stu-id="fbf64-144">OutlookTimeZoneMoveLibRedist.exe installs the Tzmovelib.dll assembly file in C:\Program Files\MsExTmz.</span></span> <span data-ttu-id="fbf64-145">请注意，第三方日历重定数据库应用程序只能重新分发安装程序、OutlookTimeZoneMoveLibRedist.exe，并且不得将程序集、Tzmovelib.dll 或任何其他提取的组件与安装程序分开重新分发。</span><span class="sxs-lookup"><span data-stu-id="fbf64-145">Note that third-party calendar rebasing applications can redistribute only the installer, OutlookTimeZoneMoveLibRedist.exe, and must not redistribute the assembly, Tzmovelib.dll, or any other extracted components separately from the installer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fbf64-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbf64-146">See also</span></span>

- [<span data-ttu-id="fbf64-147">关于将 TZDEFINITION 保存到流以提交到二进制属性</span><span class="sxs-lookup"><span data-stu-id="fbf64-147">About persisting TZDEFINITION to a stream to commit to a binary property</span></span>](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)
- [<span data-ttu-id="fbf64-148">分析二进制属性读取 TZDEFINITION 结构的流</span><span class="sxs-lookup"><span data-stu-id="fbf64-148">Parse a stream from a binary property to read the TZDEFINITION structure</span></span>](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [<span data-ttu-id="fbf64-149">分析二进制属性读取 TZREG 结构的流</span><span class="sxs-lookup"><span data-stu-id="fbf64-149">Parse a stream from a binary property to read the TZREG structure</span></span>](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
- [<span data-ttu-id="fbf64-150">从约会中读取时区属性</span><span class="sxs-lookup"><span data-stu-id="fbf64-150">Read time zone properties from an appointment</span></span>](how-to-read-time-zone-properties-from-an-appointment.md)
- [<span data-ttu-id="fbf64-151">夏令时帮助和支持中心</span><span class="sxs-lookup"><span data-stu-id="fbf64-151">Daylight Saving Time Help and Support Center</span></span>](https://support.microsoft.com/gp/cp_dst)
- [<span data-ttu-id="fbf64-152">如何使用日历更新工具Exchange夏令时</span><span class="sxs-lookup"><span data-stu-id="fbf64-152">How to address daylight saving time by using the Exchange Calendar Update Tool</span></span>](https://support.microsoft.com/kb/941018)
- [<span data-ttu-id="fbf64-153">如何使用时区数据更新工具处理时区Microsoft Office Outlook</span><span class="sxs-lookup"><span data-stu-id="fbf64-153">How to address time zone changes by using the Time Zone Data Update Tool for Microsoft Office Outlook</span></span>](https://support.microsoft.com/kb/931667)

