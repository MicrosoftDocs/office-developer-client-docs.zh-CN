---
title: 帐户
TOCTitle: Accounts
ms:assetid: 28df6dbd-4d24-42f3-91c1-fd8b3a4ea722
ms:mtpsurl: https://msdn.microsoft.com/library/office/ff184597(v=office.15)
ms:contentKeyID: 55119790
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d539f38419a8eaac60cd3054da6283a49bf4cc00
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331183"
---
# <a name="accounts"></a><span data-ttu-id="f84f8-102">帐户</span><span class="sxs-lookup"><span data-stu-id="f84f8-102">Accounts</span></span> 

<span data-ttu-id="f84f8-103">本节收录了与电子邮件帐户相关的示例任务。</span><span class="sxs-lookup"><span data-stu-id="f84f8-103">This section provides sample tasks that involve email accounts.</span></span> <span data-ttu-id="f84f8-104">例如，电子邮件帐户包括 Microsoft Exchange Server、邮局协议 3 (POP3)、Internet 消息访问协议 (IMAP) 和超文本传输协议 (HTTP) 帐户。</span><span class="sxs-lookup"><span data-stu-id="f84f8-104">Examples of email accounts are Microsoft Exchange Server, Post Office Protocol 3 (POP3), Internet Message Access Protocol (IMAP), and Hypertext Transfer Protocol (HTTP) accounts.</span></span> <span data-ttu-id="f84f8-105">当前配置文件的帐户由 [Account](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.account?view=outlook-pia) 对象表示。</span><span class="sxs-lookup"><span data-stu-id="f84f8-105">An account for the current profile is represented by an [Account](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.account?view=outlook-pia) object.</span></span>


|<span data-ttu-id="f84f8-106">主题</span><span class="sxs-lookup"><span data-stu-id="f84f8-106">Topic</span></span>|<span data-ttu-id="f84f8-107">说明</span><span class="sxs-lookup"><span data-stu-id="f84f8-107">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="f84f8-108">获取帐户信息</span><span class="sxs-lookup"><span data-stu-id="f84f8-108">Get account information</span></span>](how-to-get-account-information.md) | <span data-ttu-id="f84f8-109">将输入参数视为受信任的 Microsoft Outlook [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?view=outlook-pia) 对象，并使用 **Account** 对象来显示可用于当前 Outlook 配置文件的每个帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f84f8-109">Takes as an input argument a trusted Microsoft Outlook [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?view=outlook-pia) object, and uses the **Account** object to display the details of each account that is available for the current Outlook profile.</span></span>|
|[<span data-ttu-id="f84f8-110">为基于当前文件夹的特定帐户创建可发送项</span><span class="sxs-lookup"><span data-stu-id="f84f8-110">Create a sendable item for a specific account based on the current folder</span></span>](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md) | <span data-ttu-id="f84f8-111">包含两个代码示例，展示了如何创建可发送的电子邮件项和会议请求，并使用基于当前文件夹的特定帐户发送它们。</span><span class="sxs-lookup"><span data-stu-id="f84f8-111">Contains two code examples that show how to create a sendable email item and meeting request, and then send them by using a specific account that is based on the current folder.</span></span>|
|[<span data-ttu-id="f84f8-112">获取与文件夹关联的帐户</span><span class="sxs-lookup"><span data-stu-id="f84f8-112">Get the account for a folder</span></span>](how-to-get-the-account-for-a-folder.md) | <span data-ttu-id="f84f8-113">介绍了如何获取当前会话中与文件夹关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="f84f8-113">Gets the account that is associated with a folder in the current session.</span></span>|
|[<span data-ttu-id="f84f8-114">获取多个帐户的信息</span><span class="sxs-lookup"><span data-stu-id="f84f8-114">Get information about multiple accounts</span></span>](how-to-get-information-about-multiple-accounts.md) | <span data-ttu-id="f84f8-115">介绍了如何获取并显示当前配置文件中每个帐户的杂项信息。</span><span class="sxs-lookup"><span data-stu-id="f84f8-115">Obtains and displays miscellaneous information about each account in the current profile.</span></span>|
|[<span data-ttu-id="f84f8-116">使用 Hotmail 帐户发送邮件项</span><span class="sxs-lookup"><span data-stu-id="f84f8-116">Send a mail item by using a Hotmail account</span></span>](how-to-send-a-mail-item-by-using-a-hotmail-account.md) | <span data-ttu-id="f84f8-117">介绍了如何使用 [SendUsingAccount](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._mailitem.sendusingaccount?view=outlook-pia) 属性通过 Windows Live Hotmail 帐户发送邮件项。</span><span class="sxs-lookup"><span data-stu-id="f84f8-117">Uses the [SendUsingAccount](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._mailitem.sendusingaccount?view=outlook-pia) property to send a mail item by using a Windows Live Hotmail account.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f84f8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f84f8-118">See also</span></span>

- [<span data-ttu-id="f84f8-119">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="f84f8-119">Exchange users</span></span>](exchange-users.md)
- [<span data-ttu-id="f84f8-120">邮件</span><span class="sxs-lookup"><span data-stu-id="f84f8-120">Mail</span></span>](mail.md)
- [<span data-ttu-id="f84f8-121">收件人</span><span class="sxs-lookup"><span data-stu-id="f84f8-121">Recipients</span></span>](recipients.md)
- [<span data-ttu-id="f84f8-122">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="f84f8-122">How do I... (Outlook 2013 PIA reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)

