---
title: PROP_POP_LEAVE_ON_SERVER
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 22d7c1e8-48b9-4768-b4de-9a9f32a3aabb
description: 指定的 POP 帐户的服务器上保留邮件副本。
ms.openlocfilehash: 9f986ff60a5824ece0a8bb91619323b58ec8b87a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774439"
---
# <a name="proppopleaveonserver"></a>PROP_POP_LEAVE_ON_SERVER

指定的 POP 帐户的服务器上保留邮件副本。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符：  <br/> |0x1000  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x10000003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

下表列出了可能的值。 常量的详细信息，请参阅[常量 （帐户管理 API）](constants-account-management-api.md) 。 
  
|**可能的值**|**说明**|
|:-----|:-----|
|**LEAVE_ON_SERVER** <br/> |邮件下载到设备之后，POP 服务器上保留邮件的副本。  <br/> |
|**REMOVE_AFTER** <br/> |下载到设备之后，删除 POP 服务器邮件。  <br/> |
|**REMOVE_ON_NUKE** <br/> |仅在用户从已删除邮件文件夹中删除邮件后，请从 POP 服务器中删除邮件。  <br/> |
|**GET_REMOVE_AFTER_DAYS**( _ul_)  <br/> |获取将在其后从 POP 服务器中删除邮件的天数。  <br/> |
|**SET_REMOVE_AFTER_DAYS**（_天_）  <br/> |设置将其后从 POP 服务器中删除邮件的天数。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

