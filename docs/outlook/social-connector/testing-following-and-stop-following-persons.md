---
title: 测试关注和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍用于测试 Outlook Social Connector (OSC) 提供程序能否关注好友以及停止关注社交网络上的好友的方案。
ms.openlocfilehash: 06a2bc48fa723f4d4513376cace96a195cef9fa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432448"
---
# <a name="testing-following-and-stop-following-persons"></a>测试关注和停止关注人员

本主题介绍用于测试 Outlook Social Connector (OSC) 提供程序能否关注好友以及停止关注社交网络上的好友的方案。
  
## <a name="following-a-person"></a>跟踪人员

关注某人是使用选定用户项目提供的 SMTP 地址，将某人添加为社交网络Outlook地址。 在社交网络上跟踪某人通常涉及到通过电子邮件向该 SMTP 地址请求该人员的权限。 为了授予权限，该人员必须拥有已包含在其社交网络帐户中的 SMTP 地址，或者愿意将此 SMTP 添加到社交网络帐户。 测试以下每个方案，验证 OSC 提供程序是否正常运行。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|尝试关注社交网络上存在的人。  <br/> |对于不需要此人权限的社交网络，社交网络会立即将此人添加为好友。  <br/> 对于需要此人权限的网络，社交网络会发送通知。 "Outlook"窗格将显示此人的挂起图标。  <br/> |
|尝试关注社交网络上不存在的人。  <br/> |OSC 提供程序在 [ISocialSession：：FollowPerson](isocialsession-followperson.md) 或 [ISocialSession2：：FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。  <br/> |
|在社交网络上跟踪好友。  <br/> |对于在人员窗格中选择的朋友，将显示社交网络的徽章和该社交网络的好友个人资料图片。  <br/> |
|选择指向好友的个人资料页面的链接。  <br/> |社交网络上好友的页面将在登录用户的默认浏览器中打开。  <br/> |
   
## <a name="stop-following-a-person"></a>停止跟踪某人

停止跟踪某人是作为社交网络上的好友删除该人员。 测试以下方案以验证您的 OSC 提供程序是否停止正确跟踪某人。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|尝试删除社交网络上作为好友的人。  <br/> |社交网络不再将该用户作为已登录用户帐户上的好友列出。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

