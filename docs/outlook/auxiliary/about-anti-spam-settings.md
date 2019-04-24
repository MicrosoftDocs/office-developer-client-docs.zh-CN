---
title: 关于反垃圾邮件设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 04e00e49-c12d-4517-8574-410741d0fa06
description: Outlook 允许用户指定每个帐户的设置, 以帮助保护帐户免受垃圾邮件的阻止。 此类反垃圾邮件设置存储在用户配置文件中为该帐户指定的部分中。
ms.openlocfilehash: cf9bce058e9e0bd1c8f6f14637ae0af73f155940
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316958"
---
# <a name="about-anti-spam-settings"></a>关于反垃圾邮件设置

Outlook 允许用户指定每个帐户的设置, 以帮助保护帐户免受垃圾邮件的阻止。 此类反垃圾邮件设置存储在用户配置文件中为该帐户指定的部分中。 使用[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md)属性可获取用于存储此帐户的用户首选项 (包括反垃圾邮件设置) 的配置文件中的部分的唯一 ID (UID)。 
  
使用以下属性获取帐户的反垃圾邮件设置:
  
- [PidTagSpamJunkSenders](https://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)—指定以分号分隔的电子邮件地址和域的列表, 用户已将其指定为帐户的阻止发件人。
    
- [PidTagSpamThreshold](https://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)—指定用户为帐户指定的垃圾邮件筛选级别。 下表显示了受支持的值。
    
|支持的值 |Definition |
|:-----|:-----|
|无  <br/> |0xFFFFFFFF  <br/> |
|低  <br/> |0x00000006  <br/> |
|中等  <br/> |0x00000005  <br/> |
|高  <br/> |0x00000003  <br/> |
   
- [PidTagSpamTrustedRecipients](https://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)—指定以分号分隔的电子邮件地址和域的列表, 用户已将其指定为帐户的受信任收件人。
    
- [PidTagSpamTrustedSenders](https://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)—指定以分号分隔的电子邮件地址和域的列表, 用户已将其指定为帐户的受信任发件人。
    
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [将姓名添加到垃圾邮件筛选器列表](https://office.microsoft.com/en-us/outlook-help/add-names-to-the-junk-email-filter-lists-HA010355043.aspx?CTT=1)

