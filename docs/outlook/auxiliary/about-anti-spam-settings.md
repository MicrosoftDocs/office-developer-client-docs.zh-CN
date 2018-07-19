---
title: 有关反垃圾邮件设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 04e00e49-c12d-4517-8574-410741d0fa06
description: Outlook 允许用户指定为每个帐户的设置，可帮助保护帐户免受垃圾邮件。 此类反垃圾邮件设置存储在指定的用户的配置文件中的帐户一节。
ms.openlocfilehash: 9d1ad6fcc0748d57dd71cb80460705fcd176fae7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774156"
---
# <a name="about-anti-spam-settings"></a><span data-ttu-id="52e9d-104">有关反垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="52e9d-104">About anti-spam settings</span></span>

<span data-ttu-id="52e9d-105">Outlook 允许用户指定为每个帐户的设置，可帮助保护帐户免受垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="52e9d-105">Outlook allows users to specify settings for each account to help protect the account from spam.</span></span> <span data-ttu-id="52e9d-106">此类反垃圾邮件设置存储在指定的用户的配置文件中的帐户一节。</span><span class="sxs-lookup"><span data-stu-id="52e9d-106">Such anti-spam settings are stored in a section designated for that account in the user's profile.</span></span> <span data-ttu-id="52e9d-107">[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md)属性用于获取唯一 ID (UID) 的配置文件中存储为此帐户，包括反垃圾邮件设置的用户的首选项部分。</span><span class="sxs-lookup"><span data-stu-id="52e9d-107">Use the [PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) property to obtain the unique ID (UID) for the section in the profile that stores the user's preferences for this account, including the anti-spam settings.</span></span> 
  
<span data-ttu-id="52e9d-108">使用以下属性获取帐户的反垃圾邮件设置：</span><span class="sxs-lookup"><span data-stu-id="52e9d-108">Use the following properties to obtain anti-spam settings for the account:</span></span>
  
- <span data-ttu-id="52e9d-109">[PidTagSpamJunkSenders](http://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)— 指定分号分隔的用户帐户的阻止发件人为指定的电子邮件地址和域列表。</span><span class="sxs-lookup"><span data-stu-id="52e9d-109">[PidTagSpamJunkSenders](http://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as blocked senders for the account.</span></span>
    
- <span data-ttu-id="52e9d-110">[PidTagSpamThreshold](http://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)— 指定的垃圾邮件筛选用户指定的帐户的级别。</span><span class="sxs-lookup"><span data-stu-id="52e9d-110">[PidTagSpamThreshold](http://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)—Specifies the level of spam-filtering that the user has specified for the account.</span></span> <span data-ttu-id="52e9d-111">下表显示的受支持的值。</span><span class="sxs-lookup"><span data-stu-id="52e9d-111">The following table shows the supported values.</span></span>
    
|<span data-ttu-id="52e9d-112">受支持的值</span><span class="sxs-lookup"><span data-stu-id="52e9d-112">Supported value</span></span> |<span data-ttu-id="52e9d-113">Definition</span><span class="sxs-lookup"><span data-stu-id="52e9d-113">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="52e9d-114">无</span><span class="sxs-lookup"><span data-stu-id="52e9d-114">None</span></span>  <br/> |<span data-ttu-id="52e9d-115">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="52e9d-115">0xFFFFFFFF</span></span>  <br/> |
|<span data-ttu-id="52e9d-116">Low</span><span class="sxs-lookup"><span data-stu-id="52e9d-116">Low</span></span>  <br/> |<span data-ttu-id="52e9d-117">0x00000006</span><span class="sxs-lookup"><span data-stu-id="52e9d-117">0x00000006</span></span>  <br/> |
|<span data-ttu-id="52e9d-118">Medium</span><span class="sxs-lookup"><span data-stu-id="52e9d-118">Medium</span></span>  <br/> |<span data-ttu-id="52e9d-119">0x00000005</span><span class="sxs-lookup"><span data-stu-id="52e9d-119">0x00000005</span></span>  <br/> |
|<span data-ttu-id="52e9d-120">High</span><span class="sxs-lookup"><span data-stu-id="52e9d-120">High</span></span>  <br/> |<span data-ttu-id="52e9d-121">0x00000003</span><span class="sxs-lookup"><span data-stu-id="52e9d-121">0x00000003</span></span>  <br/> |
   
- <span data-ttu-id="52e9d-122">[PidTagSpamTrustedRecipients](http://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)— 指定分号分隔的用户已指定为受信任的帐户的收件人的电子邮件地址和域列表。</span><span class="sxs-lookup"><span data-stu-id="52e9d-122">[PidTagSpamTrustedRecipients](http://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as trusted recipients for the account.</span></span>
    
- <span data-ttu-id="52e9d-123">[PidTagSpamTrustedSenders](http://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)— 指定分号分隔的用户指定为受信任的帐户的发件人的电子邮件地址和域列表。</span><span class="sxs-lookup"><span data-stu-id="52e9d-123">[PidTagSpamTrustedSenders](http://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)—Specifies a semicolon-delimited list of email addresses and domains that the user has specified as trusted senders for the account.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="52e9d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e9d-124">See also</span></span>

- [<span data-ttu-id="52e9d-125">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="52e9d-125">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="52e9d-126">将名称添加到的垃圾邮件筛选器列表</span><span class="sxs-lookup"><span data-stu-id="52e9d-126">Add names to the Junk Email Filter lists</span></span>](http://office.microsoft.com/zh-cn/outlook-help/add-names-to-the-junk-email-filter-lists-HA010355043.aspx?CTT=1)

