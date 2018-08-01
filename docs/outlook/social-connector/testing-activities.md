---
title: 测试活动
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 98343c36-5e32-4d07-b474-adfeca693135
description: 本主题介绍测试和验证 Outlook Social Connector (OSC) 提供程序使用按需同步适当地返回活动的朋友和非朋友组成的方案。
ms.openlocfilehash: 82d24b106e8d429d20a2d396eb60155cbb95f91f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779335"
---
# <a name="testing-activities"></a>测试活动

本主题介绍测试和验证 Outlook Social Connector (OSC) 提供程序使用按需同步适当地返回活动的朋友和非朋友组成的方案。

<a name="olosc_TestingActivities_OnDemandSync"> </a>

## <a name="on-demand-synchronization"></a>按需同步

OSC 提供程序实现**ISocialProvider::GetCapabilities**，后者 OSC 调用以确定提供程序是否支持活动的朋友和非朋友组成的按需同步。 在 Outlook 人员窗格中显示的人员，OSC 获取和哈希其 SMTP 地址，调用[ISocialSession2::GetActivitiesEx](isocialsession2-getactivitiesex.md)，并将活动数据存储 （内存） 中返回这些人员。 
  
### <a name="determining-activities-to-get"></a>确定要获取的活动

传递给**GetActivitiesEx**的哈希的 SMTP 地址是确定 OSC 是否会收到的朋友或非朋友活动的关键。 OSC 获取活动的人员，如果此人他/她的社交网络帐户中指定的 SMTP 地址。 如果此人不包含的 SMTP 地址中他/她的社交网络帐户，或如果这个人正朋友但社交网络上不同的电子邮件地址， **GetActivitiesEx**不会活动的人员。 此外，对于不朋友但他/她的社交网络帐户中指定的 SMTP 地址的人员，返回的数据包括仅什么是可用于非-朋友允许由该联系人的隐私设置。 
  
### <a name="creating-test-subjects-for-friends-and-non-friends"></a>创建测试主题朋友和非朋友

若要创建朋友的测试主题，确定谁他/她的社交网络帐户中包括该地址和谁有朋友状态与登录用户的网络上的人的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 同样，若要创建非朋友的测试主题，确定谁不是按该地址，登录用户的朋友和谁具有他/她隐私设置，以允许非朋友社交网络上查看其配置文件中指定的人的 SMTP 地址。 创建包含该 SMTP 地址的电子邮件。 
  
在 Outlook 资源管理器中，选择电子邮件，其中包括朋友 （或非朋友） 中，人员窗格中显示的收件人。 在人员窗格中选择的好朋友 （或非朋友） 允许您测试提供程序提供了有关此人的信息。
  
### <a name="test-scenarios"></a>测试方案

若要验证您朋友和非朋友得到适当的活动，测试以下方案。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|在人员窗格中选择的人员是与社交网络上的登录用户朋友。  <br/> |人员窗格显示此人的配置文件和社交网络上发布配置文件图片。  <br/> |
|在人员窗格中选择的人员非朋友，登录用户的社交网络中，但已允许他/她非朋友通过查看的配置文件。  <br/> |人员窗格显示此人的配置文件和社交网络上发布配置文件图片。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [同步朋友和活动](synchronizing-friends-and-activities.md)  
- [活动的 XML](xml-for-activities.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

