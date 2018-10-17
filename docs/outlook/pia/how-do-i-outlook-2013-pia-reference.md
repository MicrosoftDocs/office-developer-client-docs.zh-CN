---
title: 如何...（Outlook 2013 PIA 参考）
TOCTitle: How do I...
ms:assetid: ff647d52-bd32-4945-afa4-5b97d9a0d7dd
ms:mtpsurl: https://msdn.microsoft.com/library/Bb612741(v=office.15)
ms:contentKeyID: 55119792
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f05f6e9199cd474a47d36ff92e255dea92a4d5cc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407553"
---
# <a name="how-do-i-outlook-2013-pia-reference"></a><span data-ttu-id="47331-102">如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="47331-102">How do I... (Outlook 2013 PIA reference)</span></span>

<span data-ttu-id="47331-103">本节包含演示如何执行 Outlook 中的某些常见任务的过程任务主题以及 Visual Basic 和 C\# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="47331-103">This section contains procedural tasks topics and code examples in Visual Basic and C# that demonstrate how to perform some common tasks in Microsoft Outlook.</span></span>

<span data-ttu-id="47331-104">若要运行这些代码示例，必须安装 Outlook 2010 和 Visual Studio 2008 或这些产品的更高版本。</span><span class="sxs-lookup"><span data-stu-id="47331-104">To run these code examples, you must have installed Outlook 2010 and Visual Studio 2008, or a later version of these products.</span></span>

<span data-ttu-id="47331-105">本节中的代码示例不要求已安装面向 Visual Studio 的 Office 开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="47331-105">The code examples in this section do not require that you have installed Office Developer Tools for Visual Studio.</span></span> <span data-ttu-id="47331-106">但是，你可以参考 [Office 开发入门](https://developer.microsoft.com/office/docs)门户来了解如何使用这些工具，以及参考 [Outlook 解决方案](https://docs.microsoft.com/visualstudio/vsto/outlook-solutions?view=vs-2017)来了解托管代码中编写的部分基本操作任务。</span><span class="sxs-lookup"><span data-stu-id="47331-106">However, you can refer to the [Getting started with Office development](https://developer.microsoft.com/office/docs) portal for information about using the tools, and refer to [Outlook solutions](https://docs.microsoft.com/visualstudio/vsto/outlook-solutions?view=vs-2017) for some basic how-to tasks written in managed code.</span></span>

<span data-ttu-id="47331-107">本节中的代码示例涵盖了从初学者到中等水平的用户，其中有些代码示例改编自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=utf8%26tag=msmsdn-20%26linkcode=as2%26camp=1789%26creative=9325%26creativeasin=0735622493)一书。</span><span class="sxs-lookup"><span data-stu-id="47331-107">Code examples in this section range from the beginner to the intermediate levels, and some of them are adapted from the book [Programming Applications for Microsoft Office Outlook 2007http://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493](https://www.amazon.com/gp/product/0735622493?ie=utf8%26tag=msmsdn-20%26linkcode=as2%26camp=1789%26creative=9325%26creativeasin=0735622493).</span></span>

<span data-ttu-id="47331-108">Office 开发人员文档团队欢迎大家发表自己的任务想法和代码示例。</span><span class="sxs-lookup"><span data-stu-id="47331-108">The Microsoft Office Developer Documentation team welcomes your task ideas and code samples! Topics tagged by the</span></span> <span data-ttu-id="47331-109">如果我们在 Outlook 内容中使用了你的代码示例，我们将会提供署名和转至你的网站的链接，以此来表达对你的工作的认可。</span><span class="sxs-lookup"><span data-stu-id="47331-109">The Microsoft Office Developer Documentation team welcomes your task ideas and code samples. If we use your code samples in Outlook content, we will recognize your work with a byline and a link to your Web site. For more information, contact us at docthis@microsoft.com.</span></span> <span data-ttu-id="47331-110">有关详细信息，请通过以下邮箱与我们联系：docthis@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="47331-110">For more information, contact us at docthis@microsoft.com.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="47331-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="47331-111">In this section</span></span> 

[<span data-ttu-id="47331-112">帐户</span><span class="sxs-lookup"><span data-stu-id="47331-112">Accounts</span></span>](accounts.md)

- [<span data-ttu-id="47331-113">获取帐户信息</span><span class="sxs-lookup"><span data-stu-id="47331-113">Get account information</span></span>](how-to-get-account-information.md)
- [<span data-ttu-id="47331-114">为基于当前文件夹的特定帐户创建可发送项</span><span class="sxs-lookup"><span data-stu-id="47331-114">Create a Sendable Item for a Specific Account Based on the Current Folder</span></span>](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md)
- [<span data-ttu-id="47331-115">获取文件夹的帐户</span><span class="sxs-lookup"><span data-stu-id="47331-115">Get the account for a folder</span></span>](how-to-get-the-account-for-a-folder.md)
- [<span data-ttu-id="47331-116">获取多个帐户的信息</span><span class="sxs-lookup"><span data-stu-id="47331-116">Get information about multiple accounts</span></span>](how-to-get-information-about-multiple-accounts.md)
- <span data-ttu-id="47331-117">[使用 Hotmail 帐户发送邮件项目](how-to-send-a-mail-item-by-using-a-hotmail-account.md)</span><span class="sxs-lookup"><span data-stu-id="47331-117">Uses the [SendUsingAccount](how-to-send-a-mail-item-by-using-a-hotmail-account.md) property to send a mail item by using a Windows Live Hotmail account.</span></span>

[<span data-ttu-id="47331-118">加载项管理</span><span class="sxs-lookup"><span data-stu-id="47331-118">Add-in Administration</span></span>](add-in-administration.md)

- [<span data-ttu-id="47331-119">确定 Outlook 是否是计算机上的即点即用应用程序</span><span class="sxs-lookup"><span data-stu-id="47331-119">Determine whether Outlook is a Click-to-Run application on a computer</span></span>](how-to-determine-whether-outlook-is-a-click-to-run-application-on-a-computer.md)


[<span data-ttu-id="47331-120">通讯簿</span><span class="sxs-lookup"><span data-stu-id="47331-120">Address Book</span></span>](address-book.md)

- [<span data-ttu-id="47331-121">在“选择姓名”对话框中显示与“联系人”文件夹对应的通讯簿</span><span class="sxs-lookup"><span data-stu-id="47331-121">Display in the Select Names dialog box the address book corresponding to a Contacts folder</span></span>](how-to-display-in-the-select-names-dialog-box-the-address-book-corresponding-to-a-contacts-folder.md)
- [<span data-ttu-id="47331-122">获取存储的全局地址列表或一组地址列表</span><span class="sxs-lookup"><span data-stu-id="47331-122">Get the Global Address List or a set of address lists for a store</span></span>](how-to-get-the-global-address-list-or-a-set-of-address-lists-for-a-store.md)
- [<span data-ttu-id="47331-123">枚举全局地址列表中的条目</span><span class="sxs-lookup"><span data-stu-id="47331-123">How to: Enumerate the Entries in the Global Address List</span></span>](how-to-enumerate-the-entries-in-the-global-address-list.md)
- [<span data-ttu-id="47331-124">显示配置文件的地址列表</span><span class="sxs-lookup"><span data-stu-id="47331-124">Display the address lists for a profile</span></span>](how-to-display-the-address-lists-for-a-profile.md)

[<span data-ttu-id="47331-125">约会</span><span class="sxs-lookup"><span data-stu-id="47331-125">Appointments</span></span>](appointments.md)

- <span data-ttu-id="47331-126">[创建属于全天事件的约会](how-to-create-an-appointment-that-is-an-all-day-event.md)</span><span class="sxs-lookup"><span data-stu-id="47331-126">Uses the [AllDayEvent](how-to-create-an-appointment-that-is-an-all-day-event.md) property to create an appointment that is an all-day event.</span></span>
- [<span data-ttu-id="47331-127">创建以太平洋时区开始、以东部时区结束的约会</span><span class="sxs-lookup"><span data-stu-id="47331-127">How to: Create an Appointment That Starts in the Pacific Time Zone and Ends in the Eastern Time Zone</span></span>](how-to-create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone.md)
- <span data-ttu-id="47331-128">[为约会项指定不同的收件人类型](how-to-specify-different-recipient-types-for-an-appointment-item.md)</span><span class="sxs-lookup"><span data-stu-id="47331-128">Uses the [OlMeetingRecipientType](how-to-specify-different-recipient-types-for-an-appointment-item.md) enumeration to specify different recipient types for an appointment item.</span></span>
- [<span data-ttu-id="47331-129">使用默认定期模式来创建定期约会</span><span class="sxs-lookup"><span data-stu-id="47331-129">Creates a recurring appointment by using the default recurrence pattern.</span></span>](how-to-create-a-recurring-appointment-by-using-the-default-recurrence-pattern.md)
- [<span data-ttu-id="47331-130">创建模式为每周一次的定期约会</span><span class="sxs-lookup"><span data-stu-id="47331-130">Create a recurring appointment that has a weekly pattern</span></span>](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md)
- [<span data-ttu-id="47331-131">创建使用 YearNth 模式的年度定期约会</span><span class="sxs-lookup"><span data-stu-id="47331-131">Create an annual recurring appointment that uses a YearNth pattern</span></span>](how-to-create-an-annual-recurring-appointment-that-uses-a-yearnth-pattern.md)
- [<span data-ttu-id="47331-132">在定期约会系列中查找特定约会</span><span class="sxs-lookup"><span data-stu-id="47331-132">Find a specific appointment in a recurring appointment series</span></span>](how-to-find-a-specific-appointment-in-a-recurring-appointment-series.md)
- [<span data-ttu-id="47331-133">在定期约会系列中创建例外约会</span><span class="sxs-lookup"><span data-stu-id="47331-133">Create an exception appointment in a recurring appointment series</span></span>](how-to-create-an-exception-appointment-in-a-recurring-appointment-series.md)
- [<span data-ttu-id="47331-134">为约会项创建提醒</span><span class="sxs-lookup"><span data-stu-id="47331-134">Create a reminder for an appointment item</span></span>](how-to-create-a-reminder-for-an-appointment-item.md)
- [<span data-ttu-id="47331-135">将约会 XML 数据导入 Outlook 约会对象</span><span class="sxs-lookup"><span data-stu-id="47331-135">Import Appointment XML Data into Outlook Appointment Objects</span></span>](how-to-import-appointment-xml-data-into-outlook-appointment-objects.md)

[<span data-ttu-id="47331-136">附件</span><span class="sxs-lookup"><span data-stu-id="47331-136">Attachments</span></span>](attachments.md)

- [<span data-ttu-id="47331-137">向邮件项附加文件</span><span class="sxs-lookup"><span data-stu-id="47331-137">Attach a File to a Mail Item</span></span>](https://docs.microsoft.com/office/vba/outlook/How-to/Items-Folders-and-Stores/attach-a-file-to-a-mail-item)
- [<span data-ttu-id="47331-138">向电子邮件附加 Outlook 联系人项目</span><span class="sxs-lookup"><span data-stu-id="47331-138">Attach an Outlook Contact Item to an Email Message</span></span>](https://docs.microsoft.com/office/vba/outlook/Concepts/Attachments/attach-an-outlook-contact-item-to-an-email-message)
- [<span data-ttu-id="47331-139">限制 Outlook 电子邮件的附件的大小</span><span class="sxs-lookup"><span data-stu-id="47331-139">Limit the Size of an Attachment to an Outlook Email Message</span></span>](https://docs.microsoft.com/office/vba/outlook/Concepts/Attachments/limit-the-size-of-an-attachment-to-an-outlook-email-message)
- [<span data-ttu-id="47331-140">修改 Outlook 电子邮件的附件</span><span class="sxs-lookup"><span data-stu-id="47331-140">Modify an Attachment of an Outlook Email Message</span></span>](https://docs.microsoft.com/office/vba/outlook/concepts/attachments/modify-an-attachment-of-an-outlook-email-message)
- [<span data-ttu-id="47331-141">以编程方式从邮件中删除安全级别为 2 的附件并将其保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="47331-141">Programmatically remove security level 2 attachments from messages and save them to disk</span></span>](how-to-programmatically-remove-security-level-2-attachments-from-messages-and-save-them-to-disk.md)

[<span data-ttu-id="47331-142">日历</span><span class="sxs-lookup"><span data-stu-id="47331-142">Calendar</span></span>](calendar.md)

- [<span data-ttu-id="47331-143">共享日历中指定时间段内闲/忙日程安排</span><span class="sxs-lookup"><span data-stu-id="47331-143">Share Free/Busy schedule within a specified period in a calendar</span></span>](how-to-share-free-busy-schedule-within-a-specified-period-in-a-calendar.md)
- [<span data-ttu-id="47331-144">通过电子邮件共享日历信息</span><span class="sxs-lookup"><span data-stu-id="47331-144">Share calendar information through email</span></span>](how-to-share-calendar-information-through-e-mail.md)
- [<span data-ttu-id="47331-145">显示收件人的共享日历</span><span class="sxs-lookup"><span data-stu-id="47331-145">Display a shared calendar of a recipient</span></span>](how-to-display-a-shared-calendar-of-a-recipient.md)
- [<span data-ttu-id="47331-146">将日历保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="47331-146">Save a calendar to disk</span></span>](how-to-save-a-calendar-to-disk.md)
- [<span data-ttu-id="47331-147">打开并显示 iCalendar 文件内容</span><span class="sxs-lookup"><span data-stu-id="47331-147">Open and display the contents of an iCalendar file</span></span>](how-to-open-and-display-the-contents-of-an-icalendar-file.md)

[<span data-ttu-id="47331-148">颜色类别</span><span class="sxs-lookup"><span data-stu-id="47331-148">Color Categories</span></span>](color-categories.md)

- [<span data-ttu-id="47331-149">枚举和添加类别</span><span class="sxs-lookup"><span data-stu-id="47331-149">Enumerate and add categories</span></span>](how-to-enumerate-and-add-categories.md)
- [<span data-ttu-id="47331-150">将类别分配给项目</span><span class="sxs-lookup"><span data-stu-id="47331-150">Assign categories to an item</span></span>](how-to-assign-categories-to-an-item.md)

[<span data-ttu-id="47331-151">联系人</span><span class="sxs-lookup"><span data-stu-id="47331-151">Contacts</span></span>](contacts.md)

- [<span data-ttu-id="47331-152">创建联系人项目</span><span class="sxs-lookup"><span data-stu-id="47331-152">Create a Contact item</span></span>](how-to-create-a-contact-item.md)
- [<span data-ttu-id="47331-153">创建自定义联系人项目</span><span class="sxs-lookup"><span data-stu-id="47331-153">Create a custom Contact item</span></span>](how-to-create-a-custom-contact-item.md)
- [<span data-ttu-id="47331-154">从 vCard 文件创建联系人项目并将此项目保存在文件夹中</span><span class="sxs-lookup"><span data-stu-id="47331-154">Create a Contact item from a vCard file and save the item in a folder</span></span>](how-to-create-a-contact-item-from-a-vcard-file-and-save-the-item-in-a-folder.md)

[<span data-ttu-id="47331-155">对话</span><span class="sxs-lookup"><span data-stu-id="47331-155">Conversations</span></span>](conversations.md)

- [<span data-ttu-id="47331-156">获取并显示对话中的项目</span><span class="sxs-lookup"><span data-stu-id="47331-156">Get and display items in a conversation</span></span>](how-to-get-and-display-items-in-a-conversation.md)
- [<span data-ttu-id="47331-157">获取并枚举选定对话</span><span class="sxs-lookup"><span data-stu-id="47331-157">Get and enumerate selected conversations</span></span>](how-to-get-and-enumerate-selected-conversations.md)

[<span data-ttu-id="47331-158">电子名片</span><span class="sxs-lookup"><span data-stu-id="47331-158">Electronic Business Cards</span></span>](electronic-business-cards.md)

- [<span data-ttu-id="47331-159">修改电子名片的布局</span><span class="sxs-lookup"><span data-stu-id="47331-159">Modify the layout of an electronic business card</span></span>](how-to-modify-the-layout-of-an-electronic-business-card.md)
- [<span data-ttu-id="47331-160">发送包含电子名片的邮件项</span><span class="sxs-lookup"><span data-stu-id="47331-160">Send a mail item with an electronic business card</span></span>](how-to-send-a-mail-item-with-an-electronic-business-card.md)

[<span data-ttu-id="47331-161">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="47331-161">Exchange Users</span></span>](exchange-users.md)

- [<span data-ttu-id="47331-162">获取当前用户的相关信息</span><span class="sxs-lookup"><span data-stu-id="47331-162">Get information about the signed in user.</span></span>](how-to-get-information-about-the-current-user.md)
- [<span data-ttu-id="47331-163">获取当前用户所属全部通讯组列表的相关信息</span><span class="sxs-lookup"><span data-stu-id="47331-163">Get information about all distribution lists of which the current user is a member</span></span>](how-to-get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member.md)
- [<span data-ttu-id="47331-164">创建通讯组列表</span><span class="sxs-lookup"><span data-stu-id="47331-164">Create a list:</span></span>](how-to-create-a-distribution-list.md)
- [<span data-ttu-id="47331-165">获取 Exchange 通讯组列表的成员</span><span class="sxs-lookup"><span data-stu-id="47331-165">Get members of an Exchange distribution list</span></span>](how-to-get-members-of-an-exchange-distribution-list.md)
- [<span data-ttu-id="47331-166">获取当前用户的经理信息</span><span class="sxs-lookup"><span data-stu-id="47331-166">Get information about the current user's manager</span></span>](how-to-get-information-about-the-current-user-s-manager.md)
- [<span data-ttu-id="47331-167">获取 Exchange 用户的经理闲/忙状态信息</span><span class="sxs-lookup"><span data-stu-id="47331-167">Get availability information for an Exchange user's manager</span></span>](how-to-get-availability-information-for-an-exchange-user-s-manager.md)
- [<span data-ttu-id="47331-168">检查经理对会议请求的响应</span><span class="sxs-lookup"><span data-stu-id="47331-168">Check a manager's response to a meeting request</span></span>](how-to-check-a-manager-s-response-to-a-meeting-request.md)
- [<span data-ttu-id="47331-169">获取当前用户的经理的直接下属的相关信息</span><span class="sxs-lookup"><span data-stu-id="47331-169">Get information about direct reports of the current user's manager</span></span>](how-to-get-information-about-direct-reports-of-the-current-user-s-manager.md)

[<span data-ttu-id="47331-170">文件夹</span><span class="sxs-lookup"><span data-stu-id="47331-170">Folders</span></span>](folders.md)

- [<span data-ttu-id="47331-171">将文件夹添加到文件夹列表</span><span class="sxs-lookup"><span data-stu-id="47331-171">Add a folder to the folder list</span></span>](how-to-add-a-folder-to-the-folder-list.md)
- [<span data-ttu-id="47331-172">枚举文件夹</span><span class="sxs-lookup"><span data-stu-id="47331-172">Enumerate folders</span></span>](how-to-enumerate-folders.md)
- [<span data-ttu-id="47331-173">获取默认文件夹并枚举它的子文件夹</span><span class="sxs-lookup"><span data-stu-id="47331-173">Get a default folder and enumerate its subfolders</span></span>](how-to-get-a-default-folder-and-enumerate-its-subfolders.md)
- [<span data-ttu-id="47331-174">基于文件夹路径获取文件夹</span><span class="sxs-lookup"><span data-stu-id="47331-174">Get a folder based on its folder path</span></span>](how-to-get-a-folder-based-on-its-folder-path.md)
- [<span data-ttu-id="47331-175">选择一个文件夹并显示文件夹信息</span><span class="sxs-lookup"><span data-stu-id="47331-175">Select a folder and display folder information</span></span>](how-to-select-a-folder-and-display-folder-information.md)
- [<span data-ttu-id="47331-176">获取文件夹的默认邮件类</span><span class="sxs-lookup"><span data-stu-id="47331-176">Get the default message class of a folder</span></span>](how-to-get-the-default-message-class-of-a-folder.md)
- [<span data-ttu-id="47331-177">访问在文件夹中存储为隐藏消息的解决方案专有数据</span><span class="sxs-lookup"><span data-stu-id="47331-177">Access solution-specific data stored as a hidden message in a folder</span></span>](how-to-access-solution-specific-data-stored-as-a-hidden-message-in-a-folder.md)
- [<span data-ttu-id="47331-178">确保文件夹级查询支持自定义项属性</span><span class="sxs-lookup"><span data-stu-id="47331-178">Ensure that custom item properties are supported in folder-level queries</span></span>](how-to-ensure-that-custom-item-properties-are-supported-in-folder-level-queries.md)

[<span data-ttu-id="47331-179">常规 Outlook 项</span><span class="sxs-lookup"><span data-stu-id="47331-179">General Outlook items</span></span>](general-outlook-items.md)

- [<span data-ttu-id="47331-180">创建用于访问常见 Outlook 项成员的帮助程序类</span><span class="sxs-lookup"><span data-stu-id="47331-180">Create a Helper class to access common Outlook item members</span></span>](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)
- [<span data-ttu-id="47331-181">显示活跃资源管理器中的选定项</span><span class="sxs-lookup"><span data-stu-id="47331-181">Display selected items in the active Explorer</span></span>](how-to-display-selected-items-in-the-active-explorer.md)

[<span data-ttu-id="47331-182">组共享</span><span class="sxs-lookup"><span data-stu-id="47331-182">Group Sharing</span></span>](group-sharing.md)

- [<span data-ttu-id="47331-183">订阅 RSS 源</span><span class="sxs-lookup"><span data-stu-id="47331-183">Subscribe to an RSS feed</span></span>](how-to-subscribe-to-an-rss-feed.md)
- [<span data-ttu-id="47331-184">将 Outlook 与 SharePoint 文件夹同步</span><span class="sxs-lookup"><span data-stu-id="47331-184">How to: Synchronize Outlook with a SharePoint Folder</span></span>](how-to-synchronize-outlook-with-a-sharepoint-folder.md)

[<span data-ttu-id="47331-185">邮件</span><span class="sxs-lookup"><span data-stu-id="47331-185">Mail</span></span>](mail.md)

- [<span data-ttu-id="47331-186">使用邮件模板创建邮件项</span><span class="sxs-lookup"><span data-stu-id="47331-186">Create a mail item by using a message template</span></span>](how-to-create-a-mail-item-by-using-a-message-template.md)
- [<span data-ttu-id="47331-187">创建邮件项，添加报表附件，并将此邮件项发送给用户的经理</span><span class="sxs-lookup"><span data-stu-id="47331-187">Create a mail item, attach a report, and send the mail item to the user's manager</span></span>](how-to-create-a-mail-item-attach-a-report-and-send-the-mail-item-to-the-user-s-manager.md)
- [<span data-ttu-id="47331-188">在帐户 SMTP 地址给定的情况下发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="47331-188">Send an E-mail Given the SMTP Address of an Account</span></span>](how-to-send-an-e-mail-given-the-smtp-address-of-an-account.md)
- [<span data-ttu-id="47331-189">向邮件项添加投票选项</span><span class="sxs-lookup"><span data-stu-id="47331-189">Add voting options to a mail item</span></span>](how-to-add-voting-options-to-a-mail-item.md)
- [<span data-ttu-id="47331-190">添加作为邮件项响应的自定义操作</span><span class="sxs-lookup"><span data-stu-id="47331-190">Add a custom action as a response to a mail item</span></span>](how-to-add-a-custom-action-as-a-response-to-a-mail-item.md)
- [<span data-ttu-id="47331-191">获取邮件项发件人的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="47331-191">Get the SMTP address of the sender of a mail item</span></span>](how-to-get-the-smtp-address-of-the-sender-of-a-mail-item.md)
- [<span data-ttu-id="47331-192">为邮件项指定不同的收件人类型</span><span class="sxs-lookup"><span data-stu-id="47331-192">Specify different recipient types for a mail item</span></span>](how-to-specify-different-recipient-types-for-a-mail-item.md)

[<span data-ttu-id="47331-193">会议请求</span><span class="sxs-lookup"><span data-stu-id="47331-193">Meeting Requests</span></span>](meeting-requests.md)

- [<span data-ttu-id="47331-194">创建会议请求，添加收件人，并指定位置</span><span class="sxs-lookup"><span data-stu-id="47331-194">Create a meeting request, add recipients, and specify a location</span></span>](how-to-create-a-meeting-request-add-recipients-and-specify-a-location.md)
- [<span data-ttu-id="47331-195">获取会议组织者</span><span class="sxs-lookup"><span data-stu-id="47331-195">Get the organizer of a meeting</span></span>](how-to-get-the-organizer-of-a-meeting.md)
- [<span data-ttu-id="47331-196">查看对会议请求的所有响应</span><span class="sxs-lookup"><span data-stu-id="47331-196">Check all responses to a meeting request</span></span>](how-to-check-all-responses-to-a-meeting-request.md)
- [<span data-ttu-id="47331-197">查找与会议请求关联的约会项</span><span class="sxs-lookup"><span data-stu-id="47331-197">Find the appointment item associated with a meeting request</span></span>](how-to-find-the-appointment-item-associated-with-a-meeting-request.md)
- [<span data-ttu-id="47331-198">自动接受会议请求</span><span class="sxs-lookup"><span data-stu-id="47331-198">Automatically accept a meeting request</span></span>](how-to-automatically-accept-a-meeting-request.md)
- [<span data-ttu-id="47331-199">提示用户响应会议请求</span><span class="sxs-lookup"><span data-stu-id="47331-199">Prompt a user to respond to a meeting request</span></span>](how-to-prompt-a-user-to-respond-to-a-meeting-request.md)

[<span data-ttu-id="47331-200">收件人</span><span class="sxs-lookup"><span data-stu-id="47331-200">Recipients</span></span>](recipients.md)

- [<span data-ttu-id="47331-201">显示“选择姓名”对话框以解析收件人</span><span class="sxs-lookup"><span data-stu-id="47331-201">Display the Select Names dialog box to resolve recipients</span></span>](how-to-display-the-select-names-dialog-box-to-resolve-recipients.md)
- <span data-ttu-id="47331-202">[使用“选择姓名”对话框获取收件人并将其分配给约会](how-to-use-the-select-names-dialog-box-to-obtain-and-assign-recipients-to-an-appointment.md)</span><span class="sxs-lookup"><span data-stu-id="47331-202">Uses the Select Names dialog box to obtain and assign recipients to an appointment item.</span></span>
- [<span data-ttu-id="47331-203">获取收件人的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="47331-203">Gets the email address type of a recipient.</span></span>](how-to-get-the-e-mail-address-of-a-recipient.md)

[<span data-ttu-id="47331-204">规则</span><span class="sxs-lookup"><span data-stu-id="47331-204">Rules</span></span>](rules.md)

- [<span data-ttu-id="47331-205">创建规则来存档来自经理的邮件项并标记这些项以进行跟踪</span><span class="sxs-lookup"><span data-stu-id="47331-205">Create a rule to file mail items from a manager and flag them for follow-up</span></span>](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)
- [<span data-ttu-id="47331-206">立即执行规则</span><span class="sxs-lookup"><span data-stu-id="47331-206">Execute a rule instantly</span></span>](how-to-execute-a-rule-instantly.md)
- [<span data-ttu-id="47331-207">在本地计算机上执行规则</span><span class="sxs-lookup"><span data-stu-id="47331-207">Execute a rule on a local computer</span></span>](how-to-execute-a-rule-on-a-local-computer.md)
- [<span data-ttu-id="47331-208">创建规则以根据主题中的多个字词为邮件项分配类别</span><span class="sxs-lookup"><span data-stu-id="47331-208">Create a rule to assign categories to mail items based on multiple words in the subject</span></span>](how-to-create-a-rule-to-assign-categories-to-mail-items-based-on-multiple-words-in-the-subject.md)


[<span data-ttu-id="47331-209">使用 Outlook 事件的示例任务</span><span class="sxs-lookup"><span data-stu-id="47331-209">Sample Tasks Using Outlook Events</span></span>](sample-tasks-using-outlook-events.md)

- [<span data-ttu-id="47331-210">为检查器实现包装并在每个检查器中跟踪项目级事件</span><span class="sxs-lookup"><span data-stu-id="47331-210">Implement a Wrapper for Inspectors and Track Item-Level Events in Each Inspector</span></span>](how-to-implement-a-wrapper-for-inspectors-and-track-item-level-events-in-each-inspector.md)

[<span data-ttu-id="47331-211">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="47331-211">Search and Filter</span></span>](search-and-filter.md)

- [<span data-ttu-id="47331-212">筛选并高效地枚举文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="47331-212">Filter and efficiently enumerate items in a folder</span></span>](how-to-filter-and-efficiently-enumerate-items-in-a-folder.md)
- [<span data-ttu-id="47331-213">使用 SetColumns 来高效地枚举文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="47331-213">Use SetColumns to efficiently enumerate items in a folder</span></span>](how-to-use-setcolumns-to-efficiently-enumerate-items-in-a-folder.md)
- [<span data-ttu-id="47331-214">使用数组来高效地枚举文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="47331-214">Use arrays to efficiently enumerate items in a folder</span></span>](how-to-use-arrays-to-efficiently-enumerate-items-in-a-folder.md)
- [<span data-ttu-id="47331-215">基于上次修改时间枚举收件箱中的项目</span><span class="sxs-lookup"><span data-stu-id="47331-215">Enumerate items in the Inbox based on the last modification time</span></span>](how-to-enumerate-items-in-the-inbox-based-on-the-last-modification-time.md)
- [<span data-ttu-id="47331-216">筛选并显示上个月修改的收件箱项目</span><span class="sxs-lookup"><span data-stu-id="47331-216">Filter and display Inbox items modified in the last month</span></span>](how-to-filter-and-display-inbox-items-modified-in-the-last-month.md)
- [<span data-ttu-id="47331-217">在枚举文件夹中的项目时筛选和显示多值属性</span><span class="sxs-lookup"><span data-stu-id="47331-217">Filter and display multivalued properties when enumerating items in a folder</span></span>](how-to-filter-and-display-multivalued-properties-when-enumerating-items-in-a-folder.md)
- [<span data-ttu-id="47331-218">在枚举文件夹中的项目时筛选和显示计算的属性</span><span class="sxs-lookup"><span data-stu-id="47331-218">This example shows how to filter and display computed properties when enumerating items in a folder.</span></span>](how-to-filter-and-display-computed-properties-when-enumerating-items-in-a-folder.md)
- [<span data-ttu-id="47331-219">枚举文件夹中的隐藏项目</span><span class="sxs-lookup"><span data-stu-id="47331-219">Enumerate hidden items in a folder</span></span>](how-to-enumerate-hidden-items-in-a-folder.md)
- [<span data-ttu-id="47331-220">使用即时搜索在所有文件夹和所有存储中搜索主题包含某短语的项目</span><span class="sxs-lookup"><span data-stu-id="47331-220">Use instant search to search all folders and all stores for a phrase in the subject</span></span>](how-to-use-instant-search-to-search-all-folders-and-all-stores-for-a-phrase-in-the-subject.md)
- [<span data-ttu-id="47331-221">在文件夹中的项目的正文中搜索某短语</span><span class="sxs-lookup"><span data-stu-id="47331-221">Search for a phrase in the body of items in a folder</span></span>](how-to-search-for-a-phrase-in-the-body-of-items-in-a-folder.md)
- [<span data-ttu-id="47331-222">在文件夹中的项目的附件中搜索某精确短语</span><span class="sxs-lookup"><span data-stu-id="47331-222">Search attachments of items in a folder for an exact phrase</span></span>](how-to-search-attachments-of-items-in-a-folder-for-an-exact-phrase.md)
- [<span data-ttu-id="47331-223">搜索并获取某个时间范围内的约会</span><span class="sxs-lookup"><span data-stu-id="47331-223">Search and obtain appointments in a time range</span></span>](how-to-search-and-obtain-appointments-in-a-time-range.md)
- [<span data-ttu-id="47331-224">筛选定期约会并在主题中搜索某个字符串</span><span class="sxs-lookup"><span data-stu-id="47331-224">Filter recurring appointments and search for a string in the subject</span></span>](how-to-filter-recurring-appointments-and-search-for-a-string-in-the-subject.md)
- [<span data-ttu-id="47331-225">搜索并在聚合视图中返回项目</span><span class="sxs-lookup"><span data-stu-id="47331-225">Search and Obtain Items in an Aggregated View</span></span>](how-to-search-and-obtain-items-in-an-aggregated-view.md)

[<span data-ttu-id="47331-226">会话</span><span class="sxs-lookup"><span data-stu-id="47331-226">Sessions</span></span>](sessions.md)

- [<span data-ttu-id="47331-227">获取并登录 Outlook 实例</span><span class="sxs-lookup"><span data-stu-id="47331-227">Get and sign in to an instance of Outlook</span></span>](how-to-get-and-log-on-to-an-instance-of-outlook.md)

[<span data-ttu-id="47331-228">存储</span><span class="sxs-lookup"><span data-stu-id="47331-228">Stores</span></span>](stores.md)

- [<span data-ttu-id="47331-229">获取配置文件中的存储的相关信息</span><span class="sxs-lookup"><span data-stu-id="47331-229">Get information about stores in a profile</span></span>](how-to-get-information-about-stores-in-a-profile.md)
- [<span data-ttu-id="47331-230">添加或删除存储</span><span class="sxs-lookup"><span data-stu-id="47331-230">Add or remove a store</span></span>](how-to-add-or-remove-a-store.md)

[<span data-ttu-id="47331-231">任务</span><span class="sxs-lookup"><span data-stu-id="47331-231">Tasks</span></span>](tasks.md)

- [<span data-ttu-id="47331-232">创建任务项</span><span class="sxs-lookup"><span data-stu-id="47331-232">Create a new task</span></span>](how-to-create-a-task-item.md)
- [<span data-ttu-id="47331-233">向收件人分配任务</span><span class="sxs-lookup"><span data-stu-id="47331-233">Assign a task to a recipient</span></span>](how-to-assign-a-task-to-a-recipient.md)
- [<span data-ttu-id="47331-234">显示发送给收件人的任务请求项</span><span class="sxs-lookup"><span data-stu-id="47331-234">Display the task request items sent to a recipient</span></span>](how-to-display-the-task-request-items-sent-to-a-recipient.md)
- [<span data-ttu-id="47331-235">响应任务请求项</span><span class="sxs-lookup"><span data-stu-id="47331-235">Respond to a task request item</span></span>](how-to-respond-to-a-task-request-item.md)
- [<span data-ttu-id="47331-236">创建定期任务</span><span class="sxs-lookup"><span data-stu-id="47331-236">Create a recurring task</span></span>](how-to-create-a-recurring-task.md)
- [<span data-ttu-id="47331-237">标记来自经理的邮件项以进行跟踪</span><span class="sxs-lookup"><span data-stu-id="47331-237">Flag mail items from a manager for follow-up</span></span>](how-to-flag-mail-items-from-a-manager-for-follow-up.md)

[<span data-ttu-id="47331-238">视图</span><span class="sxs-lookup"><span data-stu-id="47331-238">Views</span></span>](views.md)

- [<span data-ttu-id="47331-239">创建视图</span><span class="sxs-lookup"><span data-stu-id="47331-239">Create a view</span></span>](how-to-create-a-view.md)
- [<span data-ttu-id="47331-240">向视图中添加字段</span><span class="sxs-lookup"><span data-stu-id="47331-240">Add fields to a view</span></span>](how-to-add-fields-to-a-view.md)
- [<span data-ttu-id="47331-241">使用表视图枚举项</span><span class="sxs-lookup"><span data-stu-id="47331-241">Enumerate items in a table view</span></span>](how-to-enumerate-items-in-a-table-view.md)


