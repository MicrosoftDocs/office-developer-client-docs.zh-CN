---
title: 如何...（Outlook 2013 PIA 参考）
TOCTitle: How do I...
ms:assetid: ff647d52-bd32-4945-afa4-5b97d9a0d7dd
ms:mtpsurl: https://msdn.microsoft.com/library/Bb612741(v=office.15)
ms:contentKeyID: 55119792
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0bc4e19271e2747f5ffa8586b9f2ab226d6658b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355795"
---
# <a name="how-do-i-outlook-2013-pia-reference"></a>如何...（Outlook 2013 PIA 参考）

本节包含演示如何执行 Outlook 中的某些常见任务的过程任务主题以及 Visual Basic 和 C\# 代码示例。

若要运行这些代码示例，必须安装 Outlook 2010 和 Visual Studio 2008 或这些产品的更高版本。

本节中的代码示例不要求已安装面向 Visual Studio 的 Office 开发人员工具。 但是，你可以参考 [Office 开发入门](https://developer.microsoft.com/office/docs)门户来了解如何使用这些工具，以及参考 [Outlook 解决方案](https://docs.microsoft.com/visualstudio/vsto/outlook-solutions?view=vs-2017)来了解托管代码中编写的部分基本操作任务。

本节中的代码示例涵盖了从初学者到中等水平的用户，其中有些代码示例改编自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=utf8%26tag=msmsdn-20%26linkcode=as2%26camp=1789%26creative=9325%26creativeasin=0735622493)一书。

Office 开发人员文档团队欢迎大家发表自己的任务想法和代码示例。 如果我们在 Outlook 内容中使用了你的代码示例，我们将会提供署名和转至你的网站的链接，以此来表达对你的工作的认可。 有关详细信息，请通过以下邮箱与我们联系：docthis@microsoft.com。

## <a name="in-this-section"></a>本节内容 

[帐户](accounts.md)

- [获取帐户信息](how-to-get-account-information.md)
- [为基于当前文件夹的特定帐户创建可发送项](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md)
- [获取文件夹的帐户](how-to-get-the-account-for-a-folder.md)
- [获取多个帐户的信息](how-to-get-information-about-multiple-accounts.md)
- [使用 Hotmail 帐户发送邮件项目](how-to-send-a-mail-item-by-using-a-hotmail-account.md)

[加载项管理](add-in-administration.md)

- [确定 Outlook 是否是计算机上的即点即用应用程序](how-to-determine-whether-outlook-is-a-click-to-run-application-on-a-computer.md)


[通讯簿](address-book.md)

- [在“选择姓名”对话框中显示与“联系人”文件夹对应的通讯簿](how-to-display-in-the-select-names-dialog-box-the-address-book-corresponding-to-a-contacts-folder.md)
- [获取存储的全局地址列表或一组地址列表](how-to-get-the-global-address-list-or-a-set-of-address-lists-for-a-store.md)
- [枚举全局地址列表中的条目](how-to-enumerate-the-entries-in-the-global-address-list.md)
- [显示配置文件的地址列表](how-to-display-the-address-lists-for-a-profile.md)

[约会](appointments.md)

- [创建属于全天事件的约会](how-to-create-an-appointment-that-is-an-all-day-event.md)
- [创建以太平洋时区开始、以东部时区结束的约会](how-to-create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone.md)
- [为约会项指定不同的收件人类型](how-to-specify-different-recipient-types-for-an-appointment-item.md)
- [使用默认定期模式来创建定期约会](how-to-create-a-recurring-appointment-by-using-the-default-recurrence-pattern.md)
- [创建模式为每周一次的定期约会](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md)
- [创建使用 YearNth 模式的年度定期约会](how-to-create-an-annual-recurring-appointment-that-uses-a-yearnth-pattern.md)
- [在定期约会系列中查找特定约会](how-to-find-a-specific-appointment-in-a-recurring-appointment-series.md)
- [在定期约会系列中创建例外约会](how-to-create-an-exception-appointment-in-a-recurring-appointment-series.md)
- [为约会项创建提醒](how-to-create-a-reminder-for-an-appointment-item.md)
- [将约会 XML 数据导入 Outlook 约会对象](how-to-import-appointment-xml-data-into-outlook-appointment-objects.md)

[附件](attachments.md)

- [向邮件项附加文件](https://docs.microsoft.com/office/vba/outlook/How-to/Items-Folders-and-Stores/attach-a-file-to-a-mail-item)
- [向电子邮件附加 Outlook 联系人项目](https://docs.microsoft.com/office/vba/outlook/Concepts/Attachments/attach-an-outlook-contact-item-to-an-email-message)
- [限制 Outlook 电子邮件的附件的大小](https://docs.microsoft.com/office/vba/outlook/Concepts/Attachments/limit-the-size-of-an-attachment-to-an-outlook-email-message)
- [修改 Outlook 电子邮件的附件](https://docs.microsoft.com/office/vba/outlook/concepts/attachments/modify-an-attachment-of-an-outlook-email-message)
- [以编程方式从邮件中删除安全级别为 2 的附件并将其保存到磁盘](how-to-programmatically-remove-security-level-2-attachments-from-messages-and-save-them-to-disk.md)

[日历](calendar.md)

- [共享日历中指定时间段内闲/忙日程安排](how-to-share-free-busy-schedule-within-a-specified-period-in-a-calendar.md)
- [通过电子邮件共享日历信息](how-to-share-calendar-information-through-e-mail.md)
- [显示收件人的共享日历](how-to-display-a-shared-calendar-of-a-recipient.md)
- [将日历保存到磁盘](how-to-save-a-calendar-to-disk.md)
- [打开并显示 iCalendar 文件内容](how-to-open-and-display-the-contents-of-an-icalendar-file.md)

[颜色类别](color-categories.md)

- [枚举和添加类别](how-to-enumerate-and-add-categories.md)
- [将类别分配给项目](how-to-assign-categories-to-an-item.md)

[联系人](contacts.md)

- [创建联系人项目](how-to-create-a-contact-item.md)
- [创建自定义联系人项目](how-to-create-a-custom-contact-item.md)
- [从 vCard 文件创建联系人项目并将此项目保存在文件夹中](how-to-create-a-contact-item-from-a-vcard-file-and-save-the-item-in-a-folder.md)

[对话](conversations.md)

- [获取并显示对话中的项目](how-to-get-and-display-items-in-a-conversation.md)
- [获取并枚举选定对话](how-to-get-and-enumerate-selected-conversations.md)

[电子名片](electronic-business-cards.md)

- [修改电子名片的布局](how-to-modify-the-layout-of-an-electronic-business-card.md)
- [发送包含电子名片的邮件项](how-to-send-a-mail-item-with-an-electronic-business-card.md)

[Exchange 用户](exchange-users.md)

- [获取当前用户的相关信息](how-to-get-information-about-the-current-user.md)
- [获取当前用户所属全部通讯组列表的相关信息](how-to-get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member.md)
- [创建通讯组列表](how-to-create-a-distribution-list.md)
- [获取 Exchange 通讯组列表的成员](how-to-get-members-of-an-exchange-distribution-list.md)
- [获取当前用户的经理信息](how-to-get-information-about-the-current-user-s-manager.md)
- [获取 Exchange 用户的经理闲/忙状态信息](how-to-get-availability-information-for-an-exchange-user-s-manager.md)
- [检查经理对会议请求的响应](how-to-check-a-manager-s-response-to-a-meeting-request.md)
- [获取当前用户的经理的直接下属的相关信息](how-to-get-information-about-direct-reports-of-the-current-user-s-manager.md)

[文件夹](folders.md)

- [将文件夹添加到文件夹列表](how-to-add-a-folder-to-the-folder-list.md)
- [枚举文件夹](how-to-enumerate-folders.md)
- [获取默认文件夹并枚举它的子文件夹](how-to-get-a-default-folder-and-enumerate-its-subfolders.md)
- [基于文件夹路径获取文件夹](how-to-get-a-folder-based-on-its-folder-path.md)
- [选择一个文件夹并显示文件夹信息](how-to-select-a-folder-and-display-folder-information.md)
- [获取文件夹的默认邮件类](how-to-get-the-default-message-class-of-a-folder.md)
- [访问在文件夹中存储为隐藏消息的解决方案专有数据](how-to-access-solution-specific-data-stored-as-a-hidden-message-in-a-folder.md)
- [确保文件夹级查询支持自定义项属性](how-to-ensure-that-custom-item-properties-are-supported-in-folder-level-queries.md)

[常规 Outlook 项](general-outlook-items.md)

- [创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)
- [显示活跃资源管理器中的选定项](how-to-display-selected-items-in-the-active-explorer.md)

[组共享](group-sharing.md)

- [订阅 RSS 源](how-to-subscribe-to-an-rss-feed.md)
- [将 Outlook 与 SharePoint 文件夹同步](how-to-synchronize-outlook-with-a-sharepoint-folder.md)

[邮件](mail.md)

- [使用邮件模板创建邮件项](how-to-create-a-mail-item-by-using-a-message-template.md)
- [创建邮件项，添加报表附件，并将此邮件项发送给用户的经理](how-to-create-a-mail-item-attach-a-report-and-send-the-mail-item-to-the-user-s-manager.md)
- [在帐户 SMTP 地址给定的情况下发送电子邮件](how-to-send-an-e-mail-given-the-smtp-address-of-an-account.md)
- [向邮件项添加投票选项](how-to-add-voting-options-to-a-mail-item.md)
- [添加作为邮件项响应的自定义操作](how-to-add-a-custom-action-as-a-response-to-a-mail-item.md)
- [获取邮件项发件人的 SMTP 地址](how-to-get-the-smtp-address-of-the-sender-of-a-mail-item.md)
- [为邮件项指定不同的收件人类型](how-to-specify-different-recipient-types-for-a-mail-item.md)

[会议请求](meeting-requests.md)

- [创建会议请求，添加收件人，并指定位置](how-to-create-a-meeting-request-add-recipients-and-specify-a-location.md)
- [获取会议组织者](how-to-get-the-organizer-of-a-meeting.md)
- [查看对会议请求的所有响应](how-to-check-all-responses-to-a-meeting-request.md)
- [查找与会议请求关联的约会项](how-to-find-the-appointment-item-associated-with-a-meeting-request.md)
- [自动接受会议请求](how-to-automatically-accept-a-meeting-request.md)
- [提示用户响应会议请求](how-to-prompt-a-user-to-respond-to-a-meeting-request.md)

[收件人](recipients.md)

- [显示“选择姓名”对话框以解析收件人](how-to-display-the-select-names-dialog-box-to-resolve-recipients.md)
- [使用“选择姓名”对话框获取收件人并将其分配给约会](how-to-use-the-select-names-dialog-box-to-obtain-and-assign-recipients-to-an-appointment.md)
- [获取收件人的电子邮件地址](how-to-get-the-e-mail-address-of-a-recipient.md)

[规则](rules.md)

- [创建规则来存档来自经理的邮件项并标记这些项以进行跟踪](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)
- [立即执行规则](how-to-execute-a-rule-instantly.md)
- [在本地计算机上执行规则](how-to-execute-a-rule-on-a-local-computer.md)
- [创建规则以根据主题中的多个字词为邮件项分配类别](how-to-create-a-rule-to-assign-categories-to-mail-items-based-on-multiple-words-in-the-subject.md)


[使用 Outlook 事件的示例任务](sample-tasks-using-outlook-events.md)

- [为检查器实现包装并在每个检查器中跟踪项目级事件](how-to-implement-a-wrapper-for-inspectors-and-track-item-level-events-in-each-inspector.md)

[搜索和筛选](search-and-filter.md)

- [筛选并高效地枚举文件夹中的项目](how-to-filter-and-efficiently-enumerate-items-in-a-folder.md)
- [使用 SetColumns 来高效地枚举文件夹中的项目](how-to-use-setcolumns-to-efficiently-enumerate-items-in-a-folder.md)
- [使用数组来高效地枚举文件夹中的项目](how-to-use-arrays-to-efficiently-enumerate-items-in-a-folder.md)
- [基于上次修改时间枚举收件箱中的项目](how-to-enumerate-items-in-the-inbox-based-on-the-last-modification-time.md)
- [筛选并显示上个月修改的收件箱项目](how-to-filter-and-display-inbox-items-modified-in-the-last-month.md)
- [在枚举文件夹中的项目时筛选和显示多值属性](how-to-filter-and-display-multivalued-properties-when-enumerating-items-in-a-folder.md)
- [在枚举文件夹中的项目时筛选和显示计算的属性](how-to-filter-and-display-computed-properties-when-enumerating-items-in-a-folder.md)
- [枚举文件夹中的隐藏项目](how-to-enumerate-hidden-items-in-a-folder.md)
- [使用即时搜索在所有文件夹和所有存储中搜索主题包含某短语的项目](how-to-use-instant-search-to-search-all-folders-and-all-stores-for-a-phrase-in-the-subject.md)
- [在文件夹中的项目的正文中搜索某短语](how-to-search-for-a-phrase-in-the-body-of-items-in-a-folder.md)
- [在文件夹中的项目的附件中搜索某精确短语](how-to-search-attachments-of-items-in-a-folder-for-an-exact-phrase.md)
- [搜索并获取某个时间范围内的约会](how-to-search-and-obtain-appointments-in-a-time-range.md)
- [筛选定期约会并在主题中搜索某个字符串](how-to-filter-recurring-appointments-and-search-for-a-string-in-the-subject.md)
- [搜索并在聚合视图中返回项目](how-to-search-and-obtain-items-in-an-aggregated-view.md)

[会话](sessions.md)

- [获取并登录 Outlook 实例](how-to-get-and-log-on-to-an-instance-of-outlook.md)

[存储](stores.md)

- [获取配置文件中的存储的相关信息](how-to-get-information-about-stores-in-a-profile.md)
- [添加或删除存储](how-to-add-or-remove-a-store.md)

[任务](tasks.md)

- [创建任务项](how-to-create-a-task-item.md)
- [向收件人分配任务](how-to-assign-a-task-to-a-recipient.md)
- [显示发送给收件人的任务请求项](how-to-display-the-task-request-items-sent-to-a-recipient.md)
- [响应任务请求项](how-to-respond-to-a-task-request-item.md)
- [创建定期任务](how-to-create-a-recurring-task.md)
- [标记来自经理的邮件项以进行跟踪](how-to-flag-mail-items-from-a-manager-for-follow-up.md)

[视图](views.md)

- [创建视图](how-to-create-a-view.md)
- [向视图中添加字段](how-to-add-fields-to-a-view.md)
- [使用表视图枚举项](how-to-enumerate-items-in-a-table-view.md)



