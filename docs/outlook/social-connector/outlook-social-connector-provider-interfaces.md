---
title: Outlook Social Connector 提供程序接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8f92b2c7-9f47-4c84-874b-fec1a2a5b555
description: Outlook Social Connector (.osc) 是 office 客户端应用程序共享的 office 功能, 用于连接到社交和业务网络, 以便用户可以在不离开 Office 的情况下与他们的网络中的人员保持联系。
ms.openlocfilehash: 77759db34f63239473e0682cfaca720860e96768
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422808"
---
# <a name="outlook-social-connector-provider-interfaces"></a>Outlook Social Connector 提供程序接口

Outlook Social Connector (.osc) 是 office 客户端应用程序共享的 office 功能, 用于连接到社交和业务网络, 以便用户可以在不离开 Office 的情况下与他们的网络中的人员保持联系。 
  
.osc 提供程序是一种组件对象模型 (COM) DLL, 它允许 .osc 以独立于每个社交网络的 api 的方式访问社交网络数据。 下表列出了 .osc 提供程序可扩展性中的接口。 一个 .osc 提供程序必须实现五个接口中的四个, 才能与 .osc: [ISocialPerson](isocialpersoniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)、 [ISocialProvider](isocialprovideriunknown.md)和[ISocialSession](isocialsessioniunknown.md)进行通信。 如果 .osc 提供程序支持同步活动、对好友或混合同步访问好友、缓存登录凭据和使用缓存凭据登录, 或者能够关注某个人, 则提供程序应实现[ISocialSession2](isocialsession2iunknown.md), 也是如此。
  
|**名称**|**说明**|
|:-----|:-----|
|[ISocialPerson](isocialpersoniunknown.md) <br/> |表示社交网络上的人员。  <br/> |
|[ISocialProfile](isocialprofileisocialperson.md) <br/> |表示已登录的用户。  <br/> |
|[ISocialProvider](isocialprovideriunknown.md) <br/> |表示一个 .osc 提供程序的实例。  <br/> |
|[ISocialSession](isocialsessioniunknown.md) <br/> |表示与社交网络网站的连接。  <br/> |
|[ISocialSession2](isocialsession2iunknown.md) <br/> |支持通过使用缓存凭据来同步活动、添加朋友、按需或混合同步, 或登录社交网络。  <br/> |
   

