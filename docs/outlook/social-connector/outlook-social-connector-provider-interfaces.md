---
title: Outlook Social Connector 提供程序接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8f92b2c7-9f47-4c84-874b-fec1a2a5b555
description: Outlook Social Connector (OSC) 是由 Office 客户端应用程序共享 Office 功能，用于连接到社交和业务网络以便用户可以保持联系他们的网络中的人员，而不必离开办公室。
ms.openlocfilehash: bc393f32e563bbbef70538ea00cd92cf7f96729c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779325"
---
# <a name="outlook-social-connector-provider-interfaces"></a>Outlook Social Connector 提供程序接口

Outlook Social Connector (OSC) 是由 Office 客户端应用程序共享 Office 功能，用于连接到社交和业务网络以便用户可以保持联系他们的网络中的人员，而不必离开办公室。 
  
OSC 提供程序组件对象模型 (COM) 允许 OSC 访问一种方式独立于每个社交网络的 Api 中的社交网络数据的 DLL。 下表列出在 OSC 提供程序扩展性的接口。 OSC 提供程序必须实现四个与 OSC 进行通信的五个接口： [ISocialPerson](isocialpersoniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)、 [ISocialProvider](isocialprovideriunknown.md)和[ISocialSession](isocialsessioniunknown.md)。 提供程序如果 OSC 提供程序支持同步活动，按需或朋友缓存登录凭据和日志记录已使用混合同步缓存凭据或关注人员的功能，应实现[ISocialSession2](isocialsession2iunknown.md)、 以及。
  
|**名称**|**说明**|
|:-----|:-----|
|[ISocialPerson](isocialpersoniunknown.md) <br/> |表示在社交网络的人员。  <br/> |
|[ISocialProfile](isocialprofileisocialperson.md) <br/> |代表登录用户。  <br/> |
|[ISocialProvider](isocialprovideriunknown.md) <br/> |表示 OSC 提供程序的实例。  <br/> |
|[ISocialSession](isocialsessioniunknown.md) <br/> |代表与社交网络站点的连接。  <br/> |
|[ISocialSession2](isocialsession2iunknown.md) <br/> |支持同步活动，添加朋友点播或混合同步朋友或登录到使用社交网络缓存凭据。  <br/> |
   

