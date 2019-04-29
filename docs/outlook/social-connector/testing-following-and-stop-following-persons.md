---
title: 测试关注和停止关注人员
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c603c3c6-62c8-4895-93e1-b2e146dfaa4f
description: 本主题介绍了测试 Outlook Social Connector (.osc) 提供商能否关注好友以及停止关注社交网络上的好友的方案。
ms.openlocfilehash: 06a2bc48fa723f4d4513376cace96a195cef9fa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432448"
---
# <a name="testing-following-and-stop-following-persons"></a>测试关注和停止关注人员

本主题介绍了测试 Outlook Social Connector (.osc) 提供商能否关注好友以及停止关注社交网络上的好友的方案。
  
## <a name="following-a-person"></a>关注人员

若要关注某个人, 请使用所选 Outlook 项目提供的 SMTP 地址在社交网络上添加作为好友的人员。 关注社交网络的人通常需要通过电子邮件向该 SMTP 地址请求获取权限。 为了授予权限, 该用户必须具有其社交网络帐户中已包含的 smtp 地址, 或者愿意将该 smtp 添加到社交网络帐户中。 测试以下每个方案以验证您的 .osc 提供程序的行为是否正确。
  
|**方案**|**预期行为**|
|:-----|:-----|
|尝试关注社交网络上存在的社交网络上的人员。  <br/> |对于不需要此人授予权限的社交网络, 社交网络会立即将该人员添加为好友。  <br/> 对于需要来自此人的权限的网络, 社交网络发送通知。 "Outlook 人员" 窗格显示该人员的挂起图标。  <br/> |
|尝试关注社交网络上不存在的社交网络上的人员。  <br/> |.osc 提供程序在[ISocialSession:: FollowPerson](isocialsession-followperson.md)或[ISocialSession2:: FollowPersonEx](isocialsession2-followpersonex.md)中显示相应的错误。  <br/> |
|关注社交网络上的某个好友。  <br/> |对于在 "人员" 窗格中选择的朋友, 会显示社交网络的徽章和该社交网络的好友个人资料图片。  <br/> |
|选择指向好友的配置文件页的链接。  <br/> |社交网络上的好友页面在登录用户的默认浏览器中打开。  <br/> |
   
## <a name="stop-following-a-person"></a>停止关注某个人

若要停止关注某个人, 请在社交网络上将其作为好友删除。 测试以下方案以验证您的您的 .osc 提供商是否已正确停止关注某个人。
  
|**方案**|**预期行为**|
|:-----|:-----|
|试图将某个人删除为社交网络上的好友。  <br/> |社交网络不再将此人列为登录用户帐户上的好友。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

