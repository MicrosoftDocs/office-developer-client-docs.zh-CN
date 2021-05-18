---
title: 关于反垃圾邮件设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 04e00e49-c12d-4517-8574-410741d0fa06
description: Outlook允许用户为每个帐户指定设置，以帮助保护帐户免受垃圾邮件攻击。 此类反垃圾邮件设置存储在为该帐户指定的部分（在用户配置文件中）。
ms.openlocfilehash: cf9bce058e9e0bd1c8f6f14637ae0af73f155940
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316958"
---
# <a name="about-anti-spam-settings"></a><span data-ttu-id="9a9eb-104">关于反垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="9a9eb-104">About anti-spam settings</span></span>

<span data-ttu-id="9a9eb-105">Outlook允许用户为每个帐户指定设置，以帮助保护帐户免受垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-105">Outlook allows users to specify settings for each account to help protect the account from spam.</span></span> <span data-ttu-id="9a9eb-106">此类反垃圾邮件设置存储在为该帐户指定的部分（在用户配置文件中）。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-106">Such anti-spam settings are stored in a section designated for that account in the user's profile.</span></span> <span data-ttu-id="9a9eb-107">使用 [PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) 属性获取配置文件中存储此帐户的用户首选项（包括反垃圾邮件设置）中的部分的唯一 ID (UID) 。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-107">Use the [PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) property to obtain the unique ID (UID) for the section in the profile that stores the user's preferences for this account, including the anti-spam settings.</span></span> 
  
<span data-ttu-id="9a9eb-108">使用以下属性获取帐户的反垃圾邮件设置：</span><span class="sxs-lookup"><span data-stu-id="9a9eb-108">Use the following properties to obtain anti-spam settings for the account:</span></span>
  
- <span data-ttu-id="9a9eb-109">[PidTagSpamJunkSenders](https://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)— 指定用户指定为帐户阻止发件人的电子邮件地址和域的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-109">[PidTagSpamJunkSenders](https://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as blocked senders for the account.</span></span>
    
- <span data-ttu-id="9a9eb-110">[PidTagSpamThreshold](https://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)- 指定用户为帐户指定的垃圾邮件筛选级别。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-110">[PidTagSpamThreshold](https://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)—Specifies the level of spam-filtering that the user has specified for the account.</span></span> <span data-ttu-id="9a9eb-111">下表显示了支持的值。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-111">The following table shows the supported values.</span></span>
    
|<span data-ttu-id="9a9eb-112">支持的值</span><span class="sxs-lookup"><span data-stu-id="9a9eb-112">Supported value</span></span> |<span data-ttu-id="9a9eb-113">Definition</span><span class="sxs-lookup"><span data-stu-id="9a9eb-113">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="9a9eb-114">无</span><span class="sxs-lookup"><span data-stu-id="9a9eb-114">None</span></span>  <br/> |<span data-ttu-id="9a9eb-115">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="9a9eb-115">0xFFFFFFFF</span></span>  <br/> |
|<span data-ttu-id="9a9eb-116">低</span><span class="sxs-lookup"><span data-stu-id="9a9eb-116">Low</span></span>  <br/> |<span data-ttu-id="9a9eb-117">0x00000006</span><span class="sxs-lookup"><span data-stu-id="9a9eb-117">0x00000006</span></span>  <br/> |
|<span data-ttu-id="9a9eb-118">中</span><span class="sxs-lookup"><span data-stu-id="9a9eb-118">Medium</span></span>  <br/> |<span data-ttu-id="9a9eb-119">0x00000005</span><span class="sxs-lookup"><span data-stu-id="9a9eb-119">0x00000005</span></span>  <br/> |
|<span data-ttu-id="9a9eb-120">高</span><span class="sxs-lookup"><span data-stu-id="9a9eb-120">High</span></span>  <br/> |<span data-ttu-id="9a9eb-121">0x00000003</span><span class="sxs-lookup"><span data-stu-id="9a9eb-121">0x00000003</span></span>  <br/> |
   
- <span data-ttu-id="9a9eb-122">[PidTagSpamTrustedRecipients](https://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)- 指定用户指定为帐户的受信任收件人的电子邮件地址和域的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-122">[PidTagSpamTrustedRecipients](https://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as trusted recipients for the account.</span></span>
    
- <span data-ttu-id="9a9eb-123">[PidTagSpamTrustedSenders](https://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)— 指定用户指定为帐户的受信任发件人的电子邮件地址和域的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="9a9eb-123">[PidTagSpamTrustedSenders](https://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as trusted senders for the account.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9a9eb-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a9eb-124">See also</span></span>

- [<span data-ttu-id="9a9eb-125">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="9a9eb-125">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="9a9eb-126">将名称添加到垃圾邮件筛选器列表</span><span class="sxs-lookup"><span data-stu-id="9a9eb-126">Add names to the Junk Email Filter lists</span></span>](https://office.microsoft.com/en-us/outlook-help/add-names-to-the-junk-email-filter-lists-HA010355043.aspx?CTT=1)

