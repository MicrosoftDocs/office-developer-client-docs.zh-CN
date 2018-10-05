---
title: 关于反垃圾邮件设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 04e00e49-c12d-4517-8574-410741d0fa06
description: Outlook 允许用户指定为每个帐户的设置，可帮助保护帐户免受垃圾邮件。 此类反垃圾邮件设置存储在指定的用户的配置文件中的帐户一节。
ms.openlocfilehash: cf9bce058e9e0bd1c8f6f14637ae0af73f155940
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390378"
---
# <a name="about-anti-spam-settings"></a>关于反垃圾邮件设置

Outlook 允许用户指定为每个帐户的设置，可帮助保护帐户免受垃圾邮件。 此类反垃圾邮件设置存储在指定的用户的配置文件中的帐户一节。 [PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md)属性用于获取唯一 ID (UID) 的配置文件中存储为此帐户，包括反垃圾邮件设置的用户的首选项部分。 
  
使用以下属性获取帐户的反垃圾邮件设置：
  
- [PidTagSpamJunkSenders](https://msdn.microsoft.com/library/3c5182a7-7d7a-48e8-b9cb-5abd7739f0fd%28Office.15%29.aspx)— 指定分号分隔的用户帐户的阻止发件人为指定的电子邮件地址和域列表。
    
- [PidTagSpamThreshold](https://msdn.microsoft.com/library/2b2d6b8e-e3dd-4a9b-8bb5-53add675605d%28Office.15%29.aspx)— 指定的垃圾邮件筛选用户指定的帐户的级别。 下表显示的受支持的值。
    
|受支持的值 |Definition |
|:-----|:-----|
|无  <br/> |0xFFFFFFFF  <br/> |
|Low  <br/> |0x00000006  <br/> |
|Medium  <br/> |0x00000005  <br/> |
|High  <br/> |0x00000003  <br/> |
   
- [PidTagSpamTrustedRecipients](https://msdn.microsoft.com/library/59f43316-3ff6-4ed0-bc29-b31039192b08%28Office.15%29.aspx)— 指定分号分隔的用户已指定为受信任的帐户的收件人的电子邮件地址和域列表。
    
- [PidTagSpamTrustedSenders](https://msdn.microsoft.com/library/8e3f0094-e64b-4828-ba8f-5eed35f85366%28Office.15%29.aspx)— 指定分号分隔的用户指定为受信任的帐户的发件人的电子邮件地址和域列表。
    
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [将名称添加到的垃圾邮件筛选器列表](https://office.microsoft.com/en-us/outlook-help/add-names-to-the-junk-email-filter-lists-HA010355043.aspx?CTT=1)

