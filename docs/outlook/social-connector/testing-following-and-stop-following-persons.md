---
title: 测试以下和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍方案来测试按照朋友，并停止关注朋友社交网络上的 Outlook Social Connector (OSC) 提供程序的功能。
ms.openlocfilehash: 09652b658a2c20301b8b0568d373ae6fe841fe2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779324"
---
# <a name="testing-following-and-stop-following-persons"></a>测试以下和停止关注人员

本主题介绍方案来测试按照朋友，并停止关注朋友社交网络上的 Outlook Social Connector (OSC) 提供程序的功能。
  
## <a name="following-a-person"></a>关注人员

关注人员是将人员添加为朋友在社交网络中，使用提供所选 Outlook 项目的 SMTP 地址。 通常在社交网络关注某人涉及权限从请求此人的电子邮件到该 SMTP 地址。 若要授予权限，此人必须具有已包含在他或她社交网络帐户的 SMTP 地址或愿意添加到社交网络帐户的 SMTP。 测试以下每个方案若要验证您 OSC 提供程序的行为正确。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|正在尝试按照用户社交网络上存在的社交网络上的人员。  <br/> |对于不需要从此人权限社交网络，社交网络立即将此人添加为朋友。  <br/> 对于需要从该人的权限的网络，社交网络发送通知。 Outlook 人员窗格显示此人的待处理的图标。  <br/> |
|正在尝试按照用户社交网络上不存在社交网络上的人员。  <br/> |OSC 提供程序[ISocialSession::FollowPerson](isocialsession-followperson.md)或[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。  <br/> |
|跟踪社交网络上的朋友。  <br/> |在人员窗格中选择好友，显示社交网络的徽章和朋友的配置文件图片的社交网络。  <br/> |
|选择指向朋友的配置文件页面的链接。  <br/> |在登录用户的默认浏览器中打开社交网络朋友的页面。  <br/> |
   
## <a name="stop-following-a-person"></a>停止关注人员

若要停止关注人员是删除该联系人为社交网络上朋友。 测试下列方案来确认您正确关注人员的 OSC 提供程序停止。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|尝试删除为朋友社交网络上的人员。  <br/> |社交网络不再列出了为朋友登录的用户的帐户的人员。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

