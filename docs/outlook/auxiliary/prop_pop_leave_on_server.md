---
title: PROP_POP_LEAVE_ON_SERVER
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 22d7c1e8-48b9-4768-b4de-9a9f32a3aabb
description: 指定在服务器上为 POP 帐户保留邮件的副本。
ms.openlocfilehash: e1bbddea0f10c07d630676960d1b330f6055e137
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410943"
---
# <a name="prop_pop_leave_on_server"></a>PROP_POP_LEAVE_ON_SERVER

指定在服务器上为 POP 帐户保留邮件的副本。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符:  <br/> |0x1000  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x10000003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

下表列出了可能的值。 有关 [常量 (请参阅 ](constants-account-management-api.md)) 帐户管理 API 应用程序。 
  
|**可能的值**|**说明**|
|:-----|:-----|
|**LEAVE_ON_SERVER** <br/> |将邮件下载到设备后，在 POP 服务器上保留邮件的副本。  <br/> |
|**REMOVE_AFTER** <br/> |将邮件下载到设备后，从 POP 服务器中删除邮件。  <br/> |
|**REMOVE_ON_NUKE** <br/> |仅在用户从"已删除邮件"文件夹中删除邮件后，才从 POP 服务器删除邮件。  <br/> |
|**GET_REMOVE_AFTER_DAYS (** _ul_)   <br/> |获取邮件从 POP 服务器中删除的天数。  <br/> |
|**SET_REMOVE_AFTER_DAYS (**_天_)   <br/> |设置邮件从 POP 服务器中删除的天数。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

